# MediSync

MediSync is an AI-powered healthcare platform that integrates symptom analysis, disease prediction, doctor recommendations, and patient management. This project leverages a microservices architecture to provide a centralized solution for individuals seeking medical guidance and healthcare professionals overseeing patient care.

## Table of Contents

- [Introduction](#introduction)
- [Architecture](#architecture)
- [Microservices](#microservices)
- [Core Services](#core-services)
- [User Interface](#user-interface)
- [Deployment](#deployment)
- [Source Code](#source-code)
- [Development Challenges](#development-challenges)
- [References](#references)
- [Related Repositories](#related-repositories)
- [Contact Information](#contact-information)

## Introduction

MediSync aims to address the challenges faced by patients in getting timely and accurate medical help, especially in remote areas. The core features include:

- Symptom Analysis and Disease Prediction
- Doctor Recommendations
- Patient Management
- Drug Interaction Checker
- Educational Resources

The overall goal of MediSync is to make healthcare more accessible, efficient, and personalized.

## Architecture

### Architectural Diagram
![Architecture Diagram](path/to/architecture_diagram.png) <!-- TODO: Add an architectural diagram -->

### Design Decisions

- **Microservices Architecture:** The application is divided into various services to ensure resilience and scalability. Each service handles a specific functionality, making the system modular and easier to maintain.
- **Netflix Software Stack:** Utilized for service discovery, load balancing, and circuit breaking, ensuring robustness and fault tolerance.

## Microservices

### Implementation Methods

- **Netflix Software Stack:** Includes Eureka for service discovery, Ribbon for load balancing, and Hystrix for circuit breaking.

### Core Services

1. **Drug Interaction Checker Service**
   - **Functionality:** Checks for interactions between specified drugs.
   - **API Endpoints:**
     - `/ddi_checker_test (GET)`
     - `/ddi_checker (POST)`
     - `/drugs_list (GET)`
     - `/health (GET)`
     - `/status (GET)`

2. **Disease Prediction Service**
   - **Functionality:** Predicts diseases based on symptoms and recommends doctors.
   - **API Endpoints:**
     - `/predictDiseaseFromSymptoms (POST)`
     - `/recommendDoctor/disease (POST)`
     - `/recommendDoctor/symptoms (POST)`
     - `/health (GET)`
     - `/status (GET)`

3. **Appointment Scheduling Service**
   - **Functionality:** Manages doctor appointments and scheduling.
   - **API Endpoints:**
     - `/add-patient (POST)`
     - `/add-doctor (POST)`
     - `/add-hospital (POST)`
     - `/add-available-appointment (POST)`
     - `/get-available-appointments (POST)`
     - `/book-appointment (POST)`

### Discovery Server

Services register with the Eureka Discovery Server, which monitors their availability and health status. This ensures that all services can be dynamically discovered and accessed by other services.

### API Gateway

Configured using Spring Cloud Gateway, the API Gateway acts as the central entry point for routing requests to various microservices. It integrates with Eureka for dynamic routing and load balancing.

## User Interface

### Implementation Details

The user interface is built using React for the web application and Flutter for the mobile application. These frameworks provide a seamless and responsive experience for users.

### API Testing Tools

Postman was used to test the APIs during development. It allowed for efficient testing and debugging of the endpoints.

## Deployment

### Deployment Methods

- **Local Machines:** The system can be deployed on local machines using terminal commands or Docker containers.
- **Cloud Deployment:** AWS is recommended for deploying the system in the cloud due to its scalability and reliability.

### Steps for Deployment

1. **Clone the Repositories:**
   ```bash
   git clone https://github.com/ChamaliVishmani/MediSync_services.git
   git clone https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend.git
   git clone https://github.com/AsgardiansCode/medisync_ml_backend.git
   git clone https://github.com/AsgardiansCode/springboot-eureka-server.git
   git clone https://github.com/ChamaliVishmani/Medisync-api-gateway.git
   ```

## Source Code

### GitHub Links

- [Backend repo - MediSync_services](https://github.com/ChamaliVishmani/MediSync_services)
- [Frontend repo - MediSync-React-Frontend](https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend)
- [ML repo - medisync_ml_backend](https://github.com/AsgardiansCode/medisync_ml_backend)
- [Discovery Server](https://github.com/AsgardiansCode/springboot-eureka-server)
- [API Gateway](https://github.com/ChamaliVishmani/Medisync-api-gateway)

## Development Challenges

### Difficulties Faced

- **Data Privacy and Security:** Ensuring the privacy and security of sensitive health data.
- **Interoperability:** Integrating with diverse healthcare IT systems.
- **User Adoption:** Convincing both patients and doctors to adopt the new system.

### Solutions

- **Robust Security Frameworks:** Implemented advanced encryption and compliance with international standards.
- **Flexible API Design:** Developed versatile APIs for seamless data integration.
- **User-Centric Design:** Ensured the platform is intuitive and provided comprehensive training sessions.

## Related Repositories

- [Backend repo - MediSync_services](https://github.com/ChamaliVishmani/MediSync_services)
- [Frontend repo - MediSync-React-Frontend](https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend)
- [ML repo - medisync_ml_backend](https://github.com/AsgardiansCode/medisync_ml_backend)
- [Discovery Server](https://github.com/AsgardiansCode/springboot-eureka-server)
- [API Gateway](https://github.com/ChamaliVishmani/Medisync-api-gateway)
