# 🏬 Customer Store App

Aplicación **full-stack basada en microservicios** que simula una **tienda de clientes y productos**, desarrollada con **Spring Boot** (backend) y **Angular** (frontend).  
Todo el sistema puede desplegarse de forma independiente o unificada mediante **Docker Compose**.

---

## 🧩 Estructura del Proyecto
customer-store-app/
├── customer-front/ # Aplicación Angular (Frontend)
│ ├── Dockerfile
│ ├── nginx.conf
│ └── src/...
│
├── customer-back/ # Microservicio Spring Boot - Gestión de Clientes
│ └── src/main/resources/application.properties
│
├── product-backend/ # Microservicio Spring Boot - Gestión de Productos
│ └── src/main/resources/application.properties
└── README.md


---

## ⚙️ Tecnologías Utilizadas

### 🔸 Frontend (`customer-front`)
- **Angular 17+**
- **TypeScript / HTML / SCSS**
- **Servicios REST con HttpClient**
- **Nginx** (para despliegue, opcional)
- **Node.js + npm** para desarrollo local

### 🔸 Backends (`customer-back` y `product-backend`)
- **Java 21**
- **Spring Boot 3.x**
- **Spring Web / REST**
- **Springdoc OpenAPI (Swagger UI)**
- **Maven**

---

## 🧱 Descripción de los Módulos

### 🧩 1️⃣ Customer Service (`customer-back`)
Microservicio para la **gestión de clientes**, desarrollado con Spring Boot.  
Expone una API REST documentada mediante Swagger.

**Configuración (`application.properties`):**
```properties
server.port=8075
spring.application.name=BootCustomer
springdoc.swagger-ui.path=/swagger-ui.html

---


Ejecución:
cd customer-back
mvn spring-boot:run

---
Swagger UI:
👉 http://localhost:8075/swagger-ui.html

---
🧩 2️⃣ Product Service (product-backend)

Microservicio independiente para la gestión de productos.

Ejecución:
cd product-backend
mvn spring-boot:run

---
Swagger UI:
👉 http://localhost:8076/swagger-ui.html

🧩 3️⃣ Frontend Angular (customer-front)

Interfaz desarrollada en Angular que consume las APIs de los microservicios.

Ejecución local en modo desarrollo:
cd customer-front
npm install
ng serve --open

La aplicación se abrirá en:
👉 http://localhost:4200

🔗 Comunicación entre Servicios

El frontend Angular se comunica con los microservicios REST a través de peticiones HTTP:

Servicio	Puerto	Endpoint	Descripción
Customer Service	8075	/api/customers	Gestión de clientes
Product Service	8076	/api/products	Gestión de productos
🧠 Arquitectura del Sistema
┌─────────────────────────────┐
│       Angular Frontend      │
│      (customer-front)       │
└──────────────┬──────────────┘
               │ HTTP REST
┌──────────────┴──────────────┐
│     Spring Boot Services    │
│  (customer-back / product)  │
└──────────────┬──────────────┘
               │
       Base de Datos (H2/MySQL)


Cada microservicio puede ejecutarse y mantenerse de forma independiente, facilitando el escalado y despliegue modular.

🧑‍💻 Autor

Carlos Pérez de la Cueva
💼 Ingeniero en Informática de Sistemas

