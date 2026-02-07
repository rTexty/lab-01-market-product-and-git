## Product Choice
**Product**: Wildberries
**Link**: [https://wildberries.ru](https://wildberries.ru)
**Description**: Wildberries is the largest online retailer in Russia, offering a wide range of products including clothing, shoes, electronics, children's goods, and home goods. It operates a marketplace model connecting sellers with millions of customers.

## Main components

![Wildberries Component Diagram](diagrams/out/wildberries/architecture-component/Component%20Diagram.svg)

[Wildberries Component Diagram Code](diagrams/src/wildberries/architecture-component.puml)

### Selected Components

1.  **Customer Mobile App**
    *   The primary interface for customers to browse the catalog, manage their cart, place orders, and track delivery status on mobile devices (iOS/Android).

2.  **Storefront Gateway**
    *   The API Gateway that acts as the single entry point for all client requests, routing them to the appropriate backend microservices and handling cross-cutting concerns like rate limiting.

3.  **Order Management (OMS)**
    *   The central service responsible for orchestrating the entire lifecycle of an order, from creation and reservation to payment confirmation and fulfillment status updates.

4.  **Catalog & Search Service**
    *   Manages product data and provides search functionality, likely utilizing Elasticsearch to handle complex queries and filtering for the vast product inventory.

5.  **Warehouse Management (WMS)**
    *   Handles internal logistics within warehouses, including inventory tracking, bin allocation, and instructions for warehouse staff terminals.

6.  **Auth & ID Service**
    *   Manages user authentication and identity, issuing tokens for secure access to other services.

## Data flow

![Wildberries Sequence Diagram](diagrams/out/wildberries/architecture-sequence/Sequence%20Diagram.svg)

[Wildberries Sequence Diagram Code](diagrams/src/wildberries/architecture-sequence.puml)

### Group: Checkout (Reservation & Payment)

This group involves the critical steps where a user commits to an order.
**What happens:**
1.  The User clicks "Pay Now" in the App.
2.  The App sends a `createOrder` request to the **Storefront Gateway**, which forwards it to the **Order Management System (OMS)**.
3.  **OMS** requests the **Inventory Service** to reserve the stock. The Inventory Service updates the database (hard reservation) and confirms success.
4.  **OMS** saves the order as `PENDING_PAYMENT`.
5.  **OMS** initiates a transaction with the **Payment Service**.
6.  **Payment Service** contacts the **Bank**, which requests a 3DS check (Two-Factor Auth).
7.  The **Payment Service** returns the payment (3DS) URL to **OMS**, which passes it back through the **Gateway** to the **App**.
8.  The App opens a webview for the user to complete the bank's security check.

**Components involved:** WB Mobile App, Storefront Gateway, OMS, Inventory Service, Payment Service, Database, Bank.

## Deployment

![Wildberries Deployment Diagram](diagrams/out/wildberries/architecture-deployment/Deployment%20Diagram.svg)

[Wildberries Deployment Diagram Code](diagrams/src/wildberries/architecture-deployment.puml)

**Description:**
The components are deployed in a hybrid environment.
*   **Clients**: Customer and Partner apps run on consumer devices (Smartphones, Computers). Specialized hardware (PVZ PCs, Warehouse scanners) runs on-site.
*   **Cloud Infrastructure**: The backend services are hosted in a "Wildberries Global Infrastructure" (likely a private cloud or Kubernetes cluster).
*   **Compute**: Microservices are grouped into pods (E-Commerce, Logistics, Support) running in the compute cluster.
*   **Data & Middleware**: Managed clusters for Kafka (Event Bus), Redis (Cache), and Elasticsearch (Search) support the services.
*   **External**: Critical dependencies like Payment Providers and 3PL Logistics exist outside the WB infrastructure.

## Assumptions
1.  I assume the **Inventory Service** uses optimistic locking or a distributed locking mechanism on the Database to prevent race conditions when multiple users try to buy the last item simultaneously.
2.  I assume the **Storefront Gateway** implements the Backend for Frontend (BFF) pattern or similar aggregations to reduce the number of network calls the mobile app needs to make.
3.  I assume the **Search Index (Elasticsearch)** is updated asynchronously via the **Kafka Event Bus** whenever product data changes in the main DB, to ensure eventual consistency.

## Open questions
1.  How does the system handle "Split Brain" scenarios or network partitions between the WMS (Warehouse) and the central OMS, given that warehouse operations must continue even if the connection to the central cloud is flaky?
3.  How are the **Review & Ratings** data consistent with the Catalog Service? Are reviews loaded lazily by the client, or are ratings pre-calculated and stored in the product document in Elasticsearch?
