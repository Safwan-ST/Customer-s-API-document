# 📖 API Documentation

Welcome to the API documentation! This readme provides an overview of the various API endpoints available for our services, categorized into four main folders: **customer**, **general**, **tickets**, and **authentication**. Each section includes detailed information on how to use the APIs, along with examples and important parameters.

## Table of Contents
- [Headers Information](#headers-information)
- [Customer APIs](#customer-apis)
- [General APIs](#general-apis)
  - [Simple Services](#simple-services)
  - [Complex Services](#complex-services)
- [Tickets APIs](#tickets-apis)
- [Authentication APIs](#authentication-apis)

---

## 🚀 Headers Information

All requests must include the following headers:
- `lng`: Language parameter, default is `'ar'`.
- `accept`: Parameter with the value `'application/json'`.

Additionally, all customer APIs require a bearer token in the header:
- `authorization`: Parameter with the value `'Bearer {token}'`.

---

## 🧑‍💼 Customer APIs

The Customer APIs are designed to handle various customer-related functionalities, such as managing orders, profiles, and evaluations. These endpoints allow customers to interact with the services offered, book appointments, and provide feedback. Go to customer's APIs [HERE](docs/customer)

### Highlights
- **Orders Management**: Easily create, update, and track orders.
- **Profile Management**: Update personal information and redeem coupons.
- **Evaluations**: Provide feedback on services received.
- **Account Management**: Manage account settings and deletions.

---

## 🌐 General APIs

The General APIs provide access to a variety of services and product-related data. These endpoints are essential for fetching information about available services, products, and providers. They facilitate the process of searching and filtering products based on different criteria. There are two types of services within the General APIs: **Simple Services** and **Complex Services**. Go to General APIs from [HERE](docs/general)

### Simple Services
Simple services are straightforward and easy to manage. They involve basic tasks that do not require intricate scheduling or multiple steps. You can find the documentation for simple services [HERE](docs/general/SimpleServices).

### Complex Services
Complex services involve multiple steps and may require additional parameters, such as scheduling appointments or selecting specific providers. For more details on complex services, visit the [complex services documentation](docs/general/ComplexServices).

### Highlights
- **Service Information**: Fetch details about various services and products.
- **Provider Search**: Find available service providers based on specific criteria.
- **Scheduling**: Manage and pick schedules for services.

---

## 🎟️ Tickets APIs

The Tickets APIs are designed to manage support tickets. These endpoints allow customers to create, list, and manage their support requests efficiently. They ensure that customer issues are tracked and resolved promptly. The full details is [HERE](docs/tickets)

### Highlights
- **Ticket Categories**: Fetch available categories for support tickets.
- **Create Tickets**: Allow customers to submit new support tickets.
- **Manage Tickets**: List and update existing support tickets.

---

## 🔐 Authentication APIs

The Authentication APIs handle user authentication processes, including login, registration, and token management. These endpoints are crucial for ensuring secure access to the services. You can find details [HERE](docs/authentication)

### Highlights
- **User Authentication**: Manage login and registration processes.
- **Token Management**: Handle access and refresh tokens for secure communication.
