# Roles and Skills

## Components and roles

- **Customer Mobile App**
  - Mobile Engineer (iOS/Android)
  - QA Engineer (Mobile/Automation)
  - UI/UX Designer
  - Product Manager
- **Storefront Gateway**
  - Backend Engineer (High Load/Golang)
  - DevOps (+/or SRE) Engineer
- **Order Management (OMS)**
  - Backend Engineer (Java/Kotlin)
  - System Analyst
  - Database Administrator (DBA)
  - QA Engineer (Backend)
- **Catalog & Search Service**
  - Backend Engineer (Search focus)
  - Data Engineer
- **Warehouse Management (WMS)**
  - Backend Engineer
  - QA Engineer
  - Hardware/Embedded Interface Engineer
- **Auth & ID Service**
  - Security Engineer
  - Backend Engineer

## Roles and responsibilities
Below are the descriptions of responsibilities for five key roles selected from the components list above.

### 1. Mobile Engineer (iOS/Android)
**Responsibilities**: Develops and maintains the customer-facing mobile applications. They implement new features, ensure the app performs well across different devices and OS versions, fix bugs, and collaborate with designers to implement intuitive UIs. They also manage the release process to App Store and Google Play.

### 2. Backend Engineer (High Load/Microservices)
**Responsibilities**: Builds and maintains the server-side logic, APIs, and databases that power the platform. They design microservices, optimize code for high concurrency and low latency, ensure data consistency, and integrate with third-party services (like payment gateways).

### 3. Site Reliability Engineer (SRE) or DevOps 
**Responsibilities**: Ensures the reliability, scalability, and availability of production systems. They build automation for deployment (CI/CD), monitor system health (`Grafana`/`Prometheus`), handle incident response, and conduct post-mortems. They bridge the gap between development and operations.

### 4. QA Engineer (Automation)
**Responsibilities**: Designs and writes automated test scripts to verify software quality. They create test plans, execute regression tests, report defects, and integrate automated tests into the build pipeline to prevent bugs from reaching production.

### 5. Product Manager
**Responsibilities**: Defines the product vision, strategy, and roadmap. They act as the voice of the customer, gathering requirements, prioritizing features for the engineering team, analyzing metrics to measure success, and coordinating launches across different teams.

## Common skills across roles

Based on general industry requirements, these technical and soft skills are shared across most of these roles:

- **Git & Version Control**: Ability to use Git for branching, merging, and collaboration (Pull Requests).
- **Agile/Scrum Methodologies**: Understanding of iterative development, sprints, and stand-ups.
- **Basic Application Architecture**: Understanding how clients, servers, and databases interact (HTTP, REST, JSON).
- **Problem Solving**: Analytical thinking to break down complex issues into manageable solutions.
- **English Language**: Proficiency in reading technical documentation and communicating in international environments.
- **Terminal/Command Line**: Basic familiarity with shell commands for navigating and querying system state.



## My chosen role

**Role**: Golang Developer (Junior+)
[Roadmap link](https://roadmap.sh/golang)

### Skills I already have
<!-- from roadmap.sh -->
- **Go Syntax & Standard Library**: Solid understanding of structs, interfaces, and error handling patterns.
- **Web Development**: Building REST APIs using frameworks like Gin or Echo.
- **Concurrency Basics**: Familiarity with spawning Goroutines and using Channels for communication.
- **Database Interaction**: performing CRUD operations with PostgreSQL/MySQL using `database/sql` or GORM.
- **Tools**: Dependency management with Go Modules, basic Docker usage, and writing unit tests with `testing`.

### Skills I clearly lack
<!-- 4-5 skills from roadmap.sh that seemed important to have -->
- **Advanced Concurrency Patterns**: Implementing worker pools, pipelines, and handling complex synchronization/cancellation with Context.
- **Microservices Architecture**: Experience with gRPC/Protobuf, Message Brokers (Kafka/RabbitMQ), and distributed tracing.
- **Performance Optimization**: Profiling applications using `pprof`, analyzing memory allocations, and escape analysis.
- **Container Orchestration**: Deep knowledge of Kubernetes, writing Helm charts, and service meshes.
- **System Design**: Designing scalable distributed systems and implementing advanced caching strategies.

## Job market snapshot

### 1. Golang Middle (SmartContactPlatform)
- **Link**: [https://hh.ru/vacancy/130250026](https://hh.ru/vacancy/130250026?from=applicant_recommended&hhtmFrom=main)
- **Key Skills**:
  - 3+ years commercial experience.
  - Microservices architecture.
  - Message Queues (MQ) & Docker.
  - CI/CD (Jenkins/Gitlab).

### 2. Разработчик Golang Middle
- **Link**: [https://hh.ru/vacancy/130206280](https://hh.ru/vacancy/130206280?from=applicant_recommended&hhtmFrom=main)
- **Key Skills**:
  - 3+ years experience, Backend systems principles.
  - SQL, Index optimization.
  - Highload / Distributed systems patterns.
  - gRPC / Kubernetes / Performance bottlenecks.

### 3. Golang/Devops Developer
- **Link**: [https://hh.ru/vacancy/130138840](https://hh.ru/vacancy/130138840?from=applicant_recommended&hhtmFrom=main)
- **Key Skills**:
  - Server-side Golang & Microservices.
  - Docker & Linux environment.
  - Communication protocols & Database interaction.

### 4. Go-разработчик
- **Link**: [https://hh.ru/vacancy/130066643](https://hh.ru/vacancy/130066643?from=applicant_recommended&hhtmFrom=main)
- **Key Skills**:
  - Databases (SQL) & Linux familiarity.
  - gRPC, Kubernetes, Prometheus, ElasticSearch.
  - Agile practices (Scrum, Kanban).

### 5. Golang-разработчик (Рассрочки)
- **Link**: [https://hh.ru/vacancy/130049683](https://hh.ru/vacancy/130049683?hhtmFrom=vacancy_search_list)
- **Key Skills**:
  - Linux, Network basics.
  - Docker & Kubernetes (Deployment).
  - Code quality & Architecture.
  - Kafka, Redis, Monitoring (Prometheus/Grafana/ELK).

### Skills that appear in several postings
- **Docker & Kubernetes**: Mentioned in almost all postings (1, 2, 3, 4, 5) as a standard for deployment.
- **Microservices & Architecture**: A core requirement for Middle+ roles (1, 2, 3, 5).
- **SQL / Databases**: Fundamental skill for backend storage (2, 3, 4).
- **Linux Environment**: Essential for operations and deployment (3, 4, 5).
- **gRPC**: Preferred protocol for service-to-service communication (2, 4).

### Skills specific to a single posting
- **Workflow Automation**: Specific to the DevOps-heavy role (3).
- **CI/CD Tools (Jenkins/Gitlab)**: Explicit requirement for specific stacks (1).
- **Performance Bottlenecks**: Deep dive into CPU/Memory optimization (2).


## Personal reflection

### Market Trends vs. Personal Preference
However, the market dictates its own rules. The ML and AI engineering sector is currently booming. I enjoy backend development for its freedom and established popularity (among employers), but it feels like the future belongs to MLOps.

### How does my skillset compare to the market demands?
My current profile allows me to confidently handle tasks related to writing business logic and building simple REST APIs. However, the market for Middle+ positions requires not just coding skills, but a deep understanding of the **infrastructure** and **inter-service communication** that supports high-load systems. Employers are looking for engineers who can not only write Go code but also deploy, scale, and monitor it using tools like Kubernetes, Kafka, and Prometheus.

### Skills to develop this semester
1. **Microservices & gRPC**: I want to master the standard for internal communication in modern architectures. This is crucial for both pure backend and serving AI models efficiently.
2. **Container Orchestration (Kubernetes)**: Since I believe MLOps is the future, understanding how to orchestrate containers is the best transferable skill. It solidifies my backend expertise while preparing me for potential transitions into infrastructure or AI operations.