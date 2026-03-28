# Patient Management System (Microservices)

A production-ready patient management system built using **Spring Boot microservices architecture**.  
This project demonstrates real-world backend engineering concepts such as **gRPC communication, event-driven systems with Kafka, API Gateway routing, and containerization with Docker**.

---

## Tech Stack

- **Java 17**
- **Spring Boot**
- **Spring Cloud Gateway**
- **Apache Kafka**
- **gRPC (Protocol Buffers)**
- **PostgreSQL**
- **Docker & Docker Compose**
- **Maven**

---

## Architecture Overview

This system is built using **microservice architecture** with clear separation of concerns.

### Services:

- **API Gateway**
  - Entry point for all requests
  - Routing and filtering

- **Patient Service**
  - Core business logic
  - CRUD operations
  - Kafka producer
  - gRPC client

- **Billing Service**
  - Handles billing logic
  - gRPC server

- **Analytics Service**
  - Kafka consumer
  - Processes patient events asynchronously

---

## Communication Patterns

### 1. Synchronous Communication (gRPC)
- Patient Service → Billing Service
- Used during patient creation
- High performance & low latency

### 2. Asynchronous Communication (Kafka)
- Patient Service → Kafka → Analytics Service
- Event-driven architecture
- Decoupled services

---

## System Flow

1. Client sends request to API Gateway  
2. Gateway routes request to Patient Service  
3. Patient Service:
   - Validates request
   - Stores data in PostgreSQL
   - Calls Billing Service via gRPC
   - Publishes event to Kafka  
4. Analytics Service consumes event and processes it  

---

## Features

- Create, update, delete patient
- Request validation (DTO + custom validation)
- Global error handling
- gRPC-based inter-service communication
- Kafka event publishing & consuming
- API Gateway routing
- OpenAPI documentation
- Dockerized services

---

## Validation & Error Handling
- DTO-based validation (Spring Validation)
- Custom exception handling
- Global exception handler

---

## Kafka UI - Message Flow
<img width="605" height="316" alt="image" src="https://github.com/user-attachments/assets/6934df1a-c7a0-43f5-83ea-19e4bfbbf89b" />
