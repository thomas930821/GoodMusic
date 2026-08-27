# GoodMusic

**GoodMusic** is a university project developed for the course **Software Analysis and Design** during the 2024–2025 academic year.

The project is designed as a **microservices-based distributed system**, with the goal of exploring modern software architectures, service communication, scalability and containerized deployment.

## Overview

The system is divided into multiple independent services, each responsible for a specific domain of the application.

Main modules include:

* API Gateway
* Connections
* Connections API
* Reviews
* Reviews API
* Followed Reviews
* Filter
* Kafka integration

The architecture follows a distributed approach in which services can communicate both synchronously and asynchronously.

## Architecture

The project adopts a **microservices architecture**.

Each service is designed to be independently deployable and scalable, while communication between services is handled through REST APIs and asynchronous messaging.

The system includes:

* Service discovery
* API routing
* Load balancing
* Asynchronous communication
* Independent persistence
* Container orchestration

## Technologies

### Backend

* Java
* Spring Boot
* Spring Cloud Gateway
* Spring Cloud LoadBalancer
* Gradle

### Service Discovery

* Consul

Consul is used for service discovery, allowing microservices to dynamically register and locate other services within the system.

### Messaging

* Apache Kafka

Kafka is used for asynchronous communication between different parts of the architecture.

This helps decouple services and allows events to be processed independently.

### Database

* PostgreSQL

Each microservice manages its own persistent data through a dedicated PostgreSQL database, with the exception of the `filtro` service.

This approach supports data isolation between services.

### Containerization

* Docker
* Docker Compose

Docker is used to containerize the services, while Docker Compose is used to manage and orchestrate multiple containers locally.

### Orchestration

* Kubernetes

Kubernetes is used to manage container orchestration and service replicas, providing support for scalability and resilience.

## API Gateway

The system includes an API Gateway built with **Spring Cloud Gateway**.

The gateway acts as the main entry point for client requests and is responsible for routing traffic toward the appropriate microservice.

## Load Balancing

**Spring Cloud LoadBalancer** is used to distribute requests across multiple replicas of the same service.

This allows the architecture to handle increased workloads and improve service availability.

## Asynchronous Communication

Apache Kafka is used to enable event-driven communication between microservices.

This approach reduces direct dependencies between services and improves the overall modularity of the system.

## Project Structure

```text
GoodMusic/
│
├── api-gateway/
├── connessioni/
├── connessioni-api/
├── filtro/
├── kafka/
├── recensioni/
├── recensioni-api/
├── recensioni-seguite/
│
├── docker-compose.yml
├── build.gradle
├── settings.gradle
└── README.md
```

## Strengths of the Architecture

### Scalability

The use of microservices, Kafka and containerization allows individual components to be scaled independently according to workload.

### Modularity

Each microservice is responsible for a specific part of the system.

This makes the application easier to maintain, test and extend.

### Service Discovery

Consul simplifies communication between services by dynamically managing service registration and discovery.

### Resilience

Container replication and distributed services can improve availability and reduce the impact of failures affecting individual components.

## Architectural Challenges

The architecture also introduces several challenges.

### Increased Complexity

A distributed architecture requires more configuration, monitoring and coordination compared with a monolithic application.

### Single Points of Failure

Components such as Consul or the Kafka broker may become critical infrastructure dependencies if redundancy is not properly configured.

### Communication Latency

Asynchronous messaging introduces additional communication overhead compared with direct in-process communication.

### Distributed Data Management

Each microservice managing its own database improves isolation but introduces additional complexity in maintaining consistency across the system.

## Running the Project

Clone the repository:

```bash
git clone https://github.com/thomas930821/GoodMusic.git
```

Enter the project directory:

```bash
cd GoodMusic
```

Start the services using Docker Compose:

```bash
docker compose up --build
```

Depending on the local environment, additional configuration may be required for Consul, Kafka and PostgreSQL.

## Project Goals

The purpose of this project was to explore the design and implementation of distributed software systems using modern backend technologies.

In particular, the project focuses on:

* Microservices architecture
* Distributed systems
* Service discovery
* API Gateway patterns
* Asynchronous communication
* Event-driven architecture
* Containerization
* Load balancing
* Service scalability
* Independent data persistence

## Academic Project

This project was developed as part of the **Software Analysis and Design** course during the **2024–2025 academic year**.

It represents a practical application of architectural concepts related to distributed systems, microservices and scalable software design.

## Author

**Thomas Farinelli**

Computer Science Student

GitHub: [thomas930821](https://github.com/thomas930821)
