#HealthSync – Patient Management System
Author: Harsha Kumari
GitHub: harshakumari21

📌 Introduction
HealthSync is a Patient Management System built to solve real-world healthcare workflow challenges. It follows a microservices architecture to ensure modularity, scalability, and ease of deployment.

Highlights:

Centralized Authentication & Routing to streamline access control and service coordination.

Containerized Microservices for consistent environments and simplified deployments.

Efficient Communication using gRPC and Kafka for event-driven messaging.

Cloud-ready Setup with Docker-based services and PostgreSQL as database containers.

🛠️ Tools & Technologies
Backend: Java 17, Spring Boot

Security: JWT Authentication

Communication: gRPC, Kafka

Databases: PostgreSQL (Dockerized)

Infrastructure: Docker, Docker Compose

Gateway: API Gateway for routing

Testing: Postman (API Testing)

📂 Project Structure
bash
Copy
Edit
patient-management/
│
├── analytics-service/       # Handles data analytics
├── api-gateway/              # Central gateway for routing
├── api-requests/             # API request definitions
├── auth-service/             # Authentication and user management
├── billing-service/          # Billing and payments
├── grpc-requests/            # gRPC request definitions
├── integration-tests/        # End-to-end integration tests
├── patient-service/          # Core patient management
├── README.md                 # Project documentation
├── LICENSE                   # License file
└── patient-management.iml    # IntelliJ project config

⚙️ Setup & Workflow
Prerequisites
Java 17

IntelliJ IDEA (Preferred)

Docker Desktop

Postman (For API Testing)

🚀 Run Workflow
Clone the repository
git clone https://github.com/harshakumari21/patient-management.git

Open in IntelliJ IDEA and configure Docker integration.

Ensure Docker is running and network mode is set to:
--network internal

Run microservices via Docker Compose (or IntelliJ Docker configs).

🌍 Environment Variables
1. Patient-Service
BILLING_SERVICE_ADDRESS=billing-service
BILLING_SERVICE_GRPC_PORT=9001
SPRING_DATASOURCE_PASSWORD=password
SPRING_DATASOURCE_URL=jdbc:postgresql://patient-service-db:5432/db
SPRING_DATASOURCE_USERNAME=admin
SPRING_JPA_HIBERNATE_DDL_AUTO=update
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092
SPRING_SQL_INIT_MODE=always

2. Billing-Service
Bind Ports:
4001:4001
9001:9001 (gRPC)

3. Auth-Service
JWT_KEY=your_jwt_key
SPRING_DATASOURCE_PASSWORD=password
SPRING_DATASOURCE_URL=jdbc:postgresql://auth-service-db:5432/db
SPRING_DATASOURCE_USERNAME=admin
SPRING_JPA_HIBERNATE_DDL_AUTO=update
SPRING_SQL_INIT_MODE=always

4. API Gateway
Bind Port:
4004:4004

Environment Variables:
AUTH_SERVICE_URL=http://auth-service:4005

5. Analytics-Service
Bind Ports:
4002:4002

Environment Variables:
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092

6. Patient-Service-DB
Bind Port:
5000:5432
   
Bind Mount:
C:\Users\priya\IdeaProjects\patient-management\patient-service\db_modules\var\lib\postgresql\

Environment Variables:
POSTGRES_DB=db
POSTGRES_PASSWORD=password
POSTGRES_USER=admin

7. Auth-Service-DB
Bind Port:
5001:5432
   
Bind Mount:
C:\Users\priya\IdeaProjects\patient-management\auth-service\db_modules\var\lib\postgresql\data

Environment Variables:
POSTGRES_DB=db
POSTGRES_PASSWORD=password
POSTGRES_USER=admin

8. Kafka
Bind Ports:
9092:9092
9094:9094
   
Environment Variables:
KAFKA_CFG_ADVERTISED_LISTENERS=PLAINTEXT://kafka:9092,EXTERNAL://localhost:9094
KAFKA_CFG_CONTROLLER_LISTENER_NAMES=CONTROLLER
KAFKA_CFG_CONTROLLER_QUORUM_VOTERS=0@kafka:9093
KAFKA_CFG_LISTENER_SECURITY_PROTOCOL_MAP=CONTROLLER:PLAINTEXT,EXTERNAL:PLAINTEXT,PLAINTEXT:PLAINTEXT
KAFKA_CFG_LISTENERS=PLAINTEXT://:9092,CONTROLLER://:9093,EXTERNAL://:9094
KAFKA_CFG_NODE_ID=0
KAFKA_CFG_PROCESS_ROLES=controller,broker

📸 Project Architecture

✅ Key Learnings
Designed a scalable microservices system with independent deployments.

Implemented secure authentication with JWT.

Used Dockerized PostgreSQL databases for isolated development.

Integrated Kafka messaging and gRPC for efficient communication.

📬 Contact
LinkedIn: Harsha Kumari

GitHub: harshakumari21
