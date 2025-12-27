# 🚚 Logistics Microservices Platform (Backend)

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.0-F2F4F9?style=for-the-badge&logo=spring-boot)
![Docker](https://img.shields.io/badge/Docker-Enabled-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Microservices](https://img.shields.io/badge/Architecture-Distributed-red?style=for-the-badge)

## 📖 Project Overview
This repository hosts the **Backend Source Code** for a distributed logistics system. It handles the complete lifecycle of transport requests, from order creation to real-time tracking and invoicing.

**Key Architecture Features:**
* **Service Discovery:** Netflix Eureka for dynamic service registration.
* **API Gateway:** Centralized entry point routing to internal microservices.
* **Security:** Integrated with Keycloak (OAuth2/OIDC) for identity management.
* **Resilience:** Circuit Breakers implemented for fault tolerance.

## 📂 Project Structure
The solution is organized into independent microservices:

| Service Name | Description | Port |
| :--- | :--- | :--- |
| **api-gateway** | Central entry point and routing | `8080` |
| **eureka-server** | Service Registry | `8761` |
| **ms-logistica** | Core logistics logic | `Var` |
| **ms-solicitudes-v2** | Transport request management | `Var` |
| **ms-tracking-v2** | Real-time shipment tracking | `Var` |
| **ms-facturacion-v2** | Invoicing and billing system | `Var` |
| **config/keycloak** | IAM Configuration | `9090` |

## 🚀 Local Deployment Guide

### Prerequisites
* Java JDK 17
* Maven 3.8+
* Docker & Docker Compose (Recommended)

### 🔧 How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/ezequieldlv/logistics-microservices-platform.git](https://github.com/ezequieldlv/logistics-microservices-platform.git)
    ```

2.  **Infrastructure Setup:**
    Start the supporting containers (Database, Keycloak, etc.) using Docker Compose:
    ```bash
    docker-compose up -d
    ```

3.  **Build & Run Services:**
    You can run each service individually via Maven or your IDE. Ensure `eureka-server` starts first.

    ```bash
    cd transport/eureka-server
    mvn spring-boot:run
    ```

### 🧪 API Testing (Postman)
A complete **Postman Collection** (`Sistema_Transportes_TPI.postman_collection.json`) is included in the root directory to test all endpoints.

* **Gateway URL:** `http://localhost:8080`
* **Keycloak Auth:** `http://localhost:9090`

---
*Developed by **Ezequiel** - Systems Engineering Student & Aspiring SRE.*