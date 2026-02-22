# 🚀 VisionForge

### Distributed Asynchronous Image Processing Platform

------------------------------------------------------------------------

## 🎯 Project Purpose

**VisionForge** is a distributed backend platform designed to process
images asynchronously and extract structured information using OCR and
computer vision techniques.

This project was intentionally created as a **technical growth
challenge**, aiming to push our backend engineering skills beyond our
current level.

It is not just a CRUD application --- it is an engineering-focused
system built to simulate real-world backend architecture.

------------------------------------------------------------------------

## 🧠 Learning Goals

This project is designed to force growth in:

-   Advanced Spring Boot
-   Layered Architecture
-   Clean Architecture (Hexagonal)
-   SOLID principles in practice
-   JPA / Hibernate
-   Asynchronous processing
-   Message-driven architecture (RabbitMQ)
-   Automated testing
-   JWT-based security
-   Observability and logging
-   Docker-based reproducible environments

------------------------------------------------------------------------

## 🏗 High-Level Architecture

Client\
↓\
REST API (Spring Boot)\
↓\
RabbitMQ (Message Broker)\
↓\
Worker (Image Processing - OpenCV/OCR)\
↓\
PostgreSQL

------------------------------------------------------------------------

## 🔄 Execution Flow

1.  User authenticates via JWT\
2.  User uploads an image\
3.  API creates a Job (status: CREATED)\
4.  API publishes a message to RabbitMQ\
5.  Worker consumes message and sets status to RUNNING\
6.  Image processing pipeline executes\
7.  Results are persisted\
8.  Job is marked as DONE or FAILED\
9.  User queries job status and results

------------------------------------------------------------------------

## 📦 Tech Stack

-   Java 21\
-   Spring Boot\
-   Spring Security (JWT)\
-   JPA / Hibernate\
-   PostgreSQL\
-   RabbitMQ\
-   OpenCV / Tesseract / ONNX Runtime\
-   Docker\
-   JUnit 5\
-   Testcontainers\
-   GitHub Actions (CI)

------------------------------------------------------------------------

## 📂 Planned Package Structure

com.visionforge

├── api\
│ ├── controller\
│ ├── dto\
│ └── exception\
│\
├── application\
│ ├── usecase\
│ └── service\
│\
├── domain\
│ ├── model\
│ ├── enums\
│ └── repository\
│\
├── infrastructure\
│ ├── persistence\
│ ├── messaging\
│ ├── security\
│ └── vision

------------------------------------------------------------------------

## 🧩 Architectural Principles

-   Clear separation between domain and infrastructure\
-   Ports and Adapters (Hexagonal Architecture)\
-   Idempotent job processing\
-   Controlled retry strategy\
-   Explicit job state machine\
-   DTO isolation between layers\
-   Centralized exception handling

------------------------------------------------------------------------

## 🧪 Testing Strategy

-   Unit tests for domain logic (no Spring context)\
-   Repository integration tests with Testcontainers\
-   API tests using MockMvc\
-   Messaging integration tests\
-   CI pipeline executing full test suite

------------------------------------------------------------------------

## 🔐 Security

-   JWT-based authentication\
-   Resource-owner authorization model\
-   Secure password hashing\
-   Endpoint protection via Spring Security

------------------------------------------------------------------------

## 📈 Technical Roadmap

### Phase 1 --- Foundation

-   Multi-module project setup\
-   Docker Compose (Postgres + RabbitMQ)\
-   Base architecture structure

### Phase 2 --- API & Persistence

-   User and Job entities\
-   JWT authentication\
-   JPA persistence layer

### Phase 3 --- Asynchronous Worker

-   Message publishing and consumption\
-   Job state management\
-   Retry and failure handling

### Phase 4 --- Vision Pipeline

-   OpenCV integration\
-   OCR implementation\
-   Artifact storage

### Phase 5 --- Quality & Observability

-   Full automated test coverage\
-   Structured logging\
-   Metrics and monitoring\
-   CI pipeline stabilization

------------------------------------------------------------------------

## 📌 Project Status

Early development stage.\
Primary goal: structured technical growth through practical backend
engineering.
