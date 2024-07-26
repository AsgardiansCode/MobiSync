# MediSync

MediSync is an AI-powered healthcare platform that integrates symptom analysis, disease prediction, doctor recommendations, and patient management. This project leverages a microservices architecture to provide a centralized solution for individuals seeking medical guidance and healthcare professionals overseeing patient care.

## Table of Contents

- [Introduction](#introduction)
- [Architecture](#architecture)
- [Microservices](#microservices)
- [User Interface](#user-interface)
- [Deployment](#deployment)
- [Source Code](#source-code)
- [Development Challenges](#development-challenges)
- [References](#references)
- [Related Repositories](#related-repositories)
- [Contact Information](#contact-information)

## Introduction

MediSync is a comprehensive healthcare assistance platform that seamlessly integrates AI-powered symptom analysis, disease prediction, doctor recommendations, patient management, and educational resources. Built on a microservices architecture, it offers a centralized solution for both individuals seeking medical guidance and healthcare professionals overseeing patient care.

### Core Features
- **Symptom Analysis and Disease Prediction**
- **Doctor Recommendations**
- **Patient Management**
- **Drug Interaction Checker**
- **Educational Resources**
- **Emergency Services Directory**

## Architecture

### Architectural Diagram
![Architectural Diagram](TODO: Add architectural diagram here)

### Design Decisions
The architectural design of MediSync involves splitting the application into different services to enhance flexibility, scalability, and maintainability. Key decisions include:
- **Microservices Architecture:** Ensures that each service can be developed, deployed, and scaled independently.
- **Netflix Software Stack:** Utilized for service discovery, load balancing, and fault tolerance.

## Microservices

### Implementation Methods
The implementation leverages the Netflix OSS stack, including Eureka for service discovery, Ribbon for load balancing, and Hystrix for fault tolerance.

### Core Services

#### 1. Drug Interaction Checker Service

- **Functionality:** Checks for interactions between specified drugs.
- **REST API Endpoints:**
  - **/ddi_checker_test (GET):** Health check for the service.
  - **/ddi_checker (POST):** Checks for drug interactions between two drugs.
  - **/drugs_list (GET):** Returns a list of available drugs.
  - **/health (GET):** Returns the health status of the service.
  - **/status (GET):** Provides the current status of the service.
- **Inter-service Interactions:** Consumes services from the API Gateway for centralized routing.

#### 2. Disease Prediction Service

- **Functionality:** Predicts diseases based on symptoms and recommends doctors.
- **REST API Endpoints:**
  - **/predictDiseaseFromSymptoms (POST):** Predicts disease based on symptoms.
  - **/recommendDoctor/disease (POST):** Recommends a doctor based on disease.
  - **/recommendDoctor/symptoms (POST):** Recommends a doctor based on symptoms.
  - **/health (GET):** Returns the health status of the service.
  - **/status (GET):** Provides the current status of the service.
- **Inter-service Interactions:** Communicates with the Symptom Analysis Service to refine symptom data.

#### 3. Appointment Scheduling Service

- **Functionality:** Manages doctor appointments and scheduling.
- **REST API Endpoints:**
  - **/add-patient (POST):** Adds a new patient.
  - **/add-doctor (POST):** Adds a new doctor.
  - **/add-hospital (POST):** Adds a new hospital.
  - **/add-available-appointment (POST):** Adds a new available appointment.
  - **/get-available-appointments (POST):** Retrieves available appointments.
  - **/book-appointment (POST):** Books an appointment for a patient.
- **Inter-service Interactions:** Coordinates with the Doctor Recommendation Service for appointment scheduling.

#### Discovery Server
- **Role:** Services register with the discovery server, which monitors them and facilitates service discovery.
- **Technology:** Eureka Server.

#### API Gateway
- **Role:** Acts as a central entry point for routing requests to various microservices.
- **Configurations:** Utilizes Spring Cloud Gateway integrated with Eureka for dynamic service discovery and routing.

## User Interface

### Implementation Details
The user interface is implemented using React for the web application and Flutter for the mobile application. This provides a seamless and intuitive user experience across different devices.

### API Testing Tools
Postman is used for testing the application's APIs to ensure they function correctly and handle various edge cases.

## Deployment

### Deployment Methods
To deploy the system for production use, follow these steps:

#### Local Deployment
1. **Clone the repositories:**
   ```bash
   git clone https://github.com/ChamaliVishmani/MediSync_services.git
   git clone https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend.git
   git clone https://github.com/AsgardiansCode/medisync_ml_backend.git
   git clone https://github.com/AsgardiansCode/springboot-eureka-server.git
   git clone https://github.com/ChamaliVishmani/Medisync-api-gateway.git
 ```
