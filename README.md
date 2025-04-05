# Quiz and Question Microservices with Spring Boot

This project is a **Quiz and Question Microservices application** built using **Spring Boot**. It demonstrates the implementation of various microservices concepts including **service discovery**, **load balancing**, **configuration management**, and **API gateway** functionality.

## Key Features

- **Feign Client:**  
  - Used for communication between microservices, allowing declarative REST client behavior.

- **Eureka Netflix Server:**  
  - A service registry for **service discovery**, allowing microservices to find each other and communicate dynamically.

- **Eureka Netflix Client:**  
  - Each microservice registers itself with the Eureka server, enabling auto-discovery and load balancing.

- **Load Balancer:**  
  - Ensures high availability and fault tolerance by distributing incoming requests evenly across multiple service instances.

- **Config Server:**  
  - Centralized management of application configurations, simplifying updates across services.

- **API Gateway (Spring Cloud Gateway):**  
  - Acts as the entry point for all client requests, routing them to the appropriate microservice and handling cross-cutting concerns like security, logging, and rate-limiting.

## Technologies Used

- **Spring Boot**
- **Spring Cloud Netflix Eureka (Server & Client)**
- **Feign Client**
- **Spring Cloud Config Server**
- **Spring Cloud Gateway**
- **MySQL**

## How It Works

This application uses a **microservices architecture**, where each service has a specific responsibility (e.g., handling questions, quizzes, etc.). These services are:

- **Quiz Service:** Manages quiz data and handles quiz-related operations.
- **Question Service:** Handles question-related operations for quizzes.
- **Gateway Service:** API Gateway that routes requests to the appropriate services and applies cross-cutting concerns.
- **Eureka Server:** Provides service discovery for microservices.
- **Config Server:** Centralized configuration management for microservices.

### Flow of Requests

1. The client sends requests to the **API Gateway**.
2. The **API Gateway** routes requests to the appropriate microservice (Quiz or Question Service).
3. Both **Quiz Service** and **Question Service** communicate with each other through the **Feign Client**.
4. The services register themselves with the **Eureka Server** for **service discovery**.
5. **Load balancing** is handled by **Netflix Ribbon**, ensuring that requests are distributed evenly across instances of each microservice.
6. **Configuration settings** for services are centralized and managed through the **Spring Cloud Config Server**.

