# MediSync

MediSync is an AI-powered healthcare platform that integrates symptom analysis, disease prediction, doctor recommendations, and patient management. This project leverages a microservices architecture to provide a centralized solution for individuals seeking medical guidance and healthcare professionals overseeing patient care.

[![FastAPI](https://img.shields.io/badge/API-FastAPI-blue)](https://fastapi.tiangolo.com/)
[![Node.js](https://img.shields.io/badge/runtime-Node.js-green)](https://nodejs.org/)
[![React](https://img.shields.io/badge/frontend-React-blue)](https://reactjs.org/)
[![Python](https://img.shields.io/badge/language-Python-blue)](https://www.python.org/)
[![JavaScript](https://img.shields.io/badge/language-JavaScript-yellow)](https://www.javascript.com/)
[![AWS](https://img.shields.io/badge/cloud-AWS-orange)](https://aws.amazon.com/)
[![Supabase](https://img.shields.io/badge/database-Supabase-green)](https://supabase.io/)
[![PostgreSQL](https://img.shields.io/badge/database-PostgreSQL-blue)](https://www.postgresql.org/)
[![TensorFlow](https://img.shields.io/badge/ML-TensorFlow-orange)](https://www.tensorflow.org/)
[![OpenAI](https://img.shields.io/badge/AI-OpenAI-blue)](https://openai.com/)
[![Eureka](https://img.shields.io/badge/service%20discovery-Eureka-blue)](https://github.com/Netflix/eureka)
[![Docker](https://img.shields.io/badge/container-Docker-blue)](https://www.docker.com/)

### GitHub Repositories

- [Backend repo - MediSync_services](https://github.com/ChamaliVishmani/MediSync_services)
- [Frontend repo - MediSync-React-Frontend](https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend)
- [ML repo - medisync_ml_backend](https://github.com/AsgardiansCode/medisync_ml_backend)
- [Discovery Server](https://github.com/AsgardiansCode/springboot-eureka-server)
- [API Gateway](https://github.com/ChamaliVishmani/Medisync-api-gateway)
  
## Table of Contents

- [Introduction](#introduction)
- [Problem Definition](#problem-definition)
- [Proposed Solution](#proposed-solution)
- [Product Overview](#product-overview)
- [Key Features](#key-features)
- [API Endpoints](#api-endpoints)
- [Technical Architecture](#technical-architecture)
- [Microservices](#microservices)
- [User Interface](#user-interface)
- [Deployment](#deployment)
- [Source Code](#source-code)
- [Development Challenges](#development-challenges)
- [References](#references)
- [Related Repositories](#related-repositories)
- [Contact Information](#contact-information)

## Introduction

MediSync is a comprehensive healthcare assistance platform that seamlessly integrates AI-powered symptom analysis, disease prediction, doctor recommendations, patient management, and educational resources. Built on a microservices architecture, it offers a centralized solution for both individuals seeking medical guidance and healthcare professionals overseeing patient care. The core features of MediSync include:

- Symptom analysis and disease prediction
- Doctor recommendations and appointment scheduling
- Patient health logs and management
- Drug interaction checking
- Educational resources and emergency services directory

## Problem Definition

In the healthcare field, getting timely and accurate medical help is vital, especially in remote areas where resources are limited. Patients often struggle to understand their symptoms correctly, which delays them from getting the right care they need. Finding the right healthcare providers quickly is also a challenge, making the situation even more urgent. Additionally, managing medical histories and treatment plans is tough, making it hard for patients and doctors to communicate well and causing problems in how healthcare is delivered.

## Proposed Solution

MediSync aims to tackle these challenges head-on. By using AI technology and a flexible microservices architecture, MediSync aims to break down the usual barriers to accessing healthcare. It does this by offering various services like analyzing symptoms, predicting diseases, helping patients find the right doctors, managing patient records, and providing educational materials. With MediSync, we want to make healthcare more accessible, efficient, and tailored to each person's needs.

## Product Overview

### Product Description

MediSync empowers users by allowing them to input their symptoms, facilitating accurate analysis and disease prediction for informed healthcare decisions. The platform further streamlines the process by recommending suitable doctors based on specialty, location, and availability, simplifying appointment scheduling. Users can also maintain comprehensive health records, access educational materials, and receive personalized health tips, ensuring they have the tools and information needed to manage their health effectively.

### Uniqueness

What sets MediSync apart is not only its advanced features but also its robust architecture. Leveraging microservices, the platform ensures resilience and reliability. Even if one service experiences downtime, the rest of the system remains operational, minimizing disruptions and ensuring uninterrupted access to critical healthcare services.

## Key Features

### Symptom Analysis and Disease Prediction
- **Symptom Input and Auto-suggestions:** Users can input symptoms and receive auto-suggestions for accurate symptom analysis.
- **NLP-based Symptom Clarification:** Utilizes NLP to clarify symptoms and provide a detailed analysis.
- **Disease Prediction:** AI models predict potential diseases based on the symptoms provided.

### Doctor Recommendations
- **Specialist Recommendations:** Recommends suitable doctors based on the predicted disease or symptoms.
- **Doctor Channeling:** Facilitates appointment scheduling with recommended doctors.

### Patient Management
- **Health Logs and History:** Users can maintain comprehensive health records, including daily logs, treatment plans, and medication adherence.
- **Health Data Visualization:** Provides visualizations and reports of health data for better management.

### Drug Interaction Checker
- **Interaction Level:** Checks for interactions between specified drugs and provides the interaction level.
- **Available Drugs:** Lists available drugs for interaction checks.

### Educational Resources
- **Health Tips and Guidelines:** Offers personalized health tips, dietary suggestions, exercise routines, and educational materials.
- **Emergency Services Directory:** Provides quick access to emergency numbers and contacts for nearby hospitals.

## API Endpoints

### Drug Interaction Checker Service

1. **/ddi_checker_test (GET):**
   - **Description:** A simple health check for the drug interaction checker service.
   - **Response:** Confirmation message that the drug interaction checker is registered.
   
2. **/ddi_checker (POST):**
   - **Description:** Checks for drug interactions between two specified drugs.
   - **Request Body:**
     ```json
     {
       "drugA": "DrugNameA",
       "drugB": "DrugNameB"
     }
     ```
   - **Response:** Interaction level between the specified drugs.
   
3. **/drugs_list (GET):**
   - **Description:** Returns a list of available drugs that can be checked for interactions.
   - **Response:** Lists of drug names for drugA and drugB.
   
4. **/health (GET):**
   - **Description:** Checks the health status of the drug interaction checker service.
   - **Response:** Status message indicating the health of the service.
   
5. **/status (GET):**
   - **Description:** Provides the current status of the drug interaction checker service.
   - **Response:** Status message indicating that the service is running.

### Disease Prediction Service

1. **/predictDiseaseFromSymptoms (POST):**
   - **Description:** Predicts the disease based on the given symptoms.
   - **Request Body:**
     ```json
     {
       "symptoms": "symptom1, symptom2, symptom3"
     }
     ```
   - **Response:** Predicted disease based on the symptoms provided.
   
2. **/recommendDoctor/disease (POST):**
   - **Description:** Recommends a doctor based on the given disease.
   - **Request Body:**
     ```json
     {
       "disease": "DiseaseName"
     }
     ```
   - **Response:** Recommended doctor for the given disease.
   
3. **/recommendDoctor/symptoms (POST):**
   - **Description:** Recommends a doctor based on the given symptoms by first predicting the disease.
   - **Request Body:**
     ```json
     {
       "symptoms": "symptom1, symptom2, symptom3"
     }
     ```
   - **Response:** Recommended doctor for the predicted disease based on the symptoms provided.
   
4. **/health (GET):**
   - **Description:** Checks the health status of the disease prediction service.
   - **Response:** Status message indicating the health of the service.
   
5. **/status (GET):**
   - **Description:** Provides the current status of the disease prediction service.
   - **Response:** Status message indicating that the service is running.

### Appointment Scheduling Service

1. **/add-patient (POST):**
   - **Description:** Adds a new patient to the database.
   - **Request Body:**
     ```json
     {
       "name": "John Doe",
       "age": 30,
       "email": "johndoe@example.com"
     }
     ```
     
2. **/add-doctor (POST):**
   - **Description:** Adds a new doctor to the database.
   - **Request Body:**
     ```json
     {
       "name": "Dr. Smith",
       "email": "drsmith@example.com",
       "specialty": "Cardiology",
       "hospital_id": 1
     }
     ```
     
3. **/add-hospital (POST):**
   - **Description:** Adds a new hospital to the database.
   - **Request Body:**
     ```json
     {
       "name": "City Hospital",
       "location": "123 Main St, Cityville"
     }
     ```
     
4. **/add-available-appointment (POST):**
   - **Description:** Adds a new available appointment for a doctor.
   - **Request Body:**
     ```json
     {
       "doctor_id": 1,
       "hospital_id": 1,
       "appointment_date": "2024-08-01T10:00:00.000Z"
     }
     ```
     
5. **/get-available-appointments (POST):**
   - **Description:** Retrieves available appointments based on specialty.
   - **Request Body:**
     ```json
     {
       "specialty": "Cardiology"
     }
     ```
     
6. **/book-appointment (POST):**
   - **Description:** Books an appointment for a patient.
   - **Request Body:**
     ```json
     {
       "patientId": 1,
       "patientEmail": "johndoe@example.com",
       "appointmentId": 1
     }
     ```

## Technical Architecture

### Architectural Diagram
![WhatsApp Image 2024-07-24 at 22 51 21_182568bc](https://github.com/user-attachments/assets/cdcce51b-0746-44c8-93bb-77e3cfecfe00)

### Design Decisions
The MediSync platform utilizes a microservices architecture to ensure scalability, maintainability, and flexibility. The application is divided into several core services, each responsible for a specific functionality. This approach allows for independent development, deployment, and scaling of each service, enhancing the overall reliability and resilience of the system.

## Microservices

### Implementation Methods
MediSync's microservices are implemented using a combination of FastAPI for Python-based services and Node.js for JavaScript-based services. The Netflix software stack, including Eureka for service discovery and Spring Cloud Gateway for API Gateway, is used to manage the microservices architecture.

### Core Services

#### Symptom Analysis Service
- **Purpose:** Utilizes NLP and AI to analyze symptoms input by users and clarifies them through an interactive process.
- **API Endpoints:**
  - `/analyzeSymptoms` (POST): Analyzes the provided symptoms and returns possible diseases.
  - `/clarifySymptoms` (POST): Interactively asks follow-up questions to clarify symptoms.
  - `/getSymptomSuggestions` (GET): Provides auto-suggestions for symptom input.
  - `/health` (GET): Checks the health status of the service.
- **Inter-service Interactions:** Consumes services from the Disease Prediction Service to provide accurate disease predictions.

#### Disease Prediction Service
- **Purpose:** Predicts diseases based on analyzed symptoms and recommends doctors.
- **API Endpoints:**
  - `/predictDiseaseFromSymptoms` (POST): Predicts diseases based on symptoms.
  - `/recommendDoctor/disease` (POST): Recommends a doctor based on the disease.
  - `/recommendDoctor/symptoms` (POST): Recommends a doctor based on symptoms.
  - `/health` (GET): Checks the health status of the service.
- **Inter-service Interactions:** Provides disease predictions and doctor recommendations to the Symptom Analysis Service.

#### Appointment Scheduling Service
- **Purpose:** Manages patient appointments with doctors.
- **API Endpoints:**
  - `/add-patient` (POST): Adds a new patient.
  - `/add-doctor` (POST): Adds a new doctor.
  - `/add-hospital` (POST): Adds a new hospital.
  - `/add-available-appointment` (POST): Adds a new available appointment.
  - `/get-available-appointments` (POST): Retrieves available appointments.
  - `/book-appointment` (POST): Books an appointment for a patient.
- **Inter-service Interactions:** Interacts with the Patient Management Service for patient data and the Doctor Recommendation Service for available doctors.

#### Drug Interaction Checker Service
- **Purpose:** Checks for drug interactions between specified drugs.
- **API Endpoints:**
  - `/ddi_checker_test` (GET): Health check for the service.
  - `/ddi_checker` (POST): Checks for drug interactions between two drugs.
  - `/drugs_list` (GET): Lists available drugs for interaction checks.
  - `/health` (GET): Checks the health status of the service.
  - `/status` (GET): Provides the current status of the service.
- **Inter-service Interactions:** Consumes drug data from the Drug Database Service.

### Discovery Server
The Discovery Server is implemented using Eureka, allowing services to register themselves and discover other services dynamically. This setup ensures high availability and load balancing.

### API Gateway
The API Gateway is built using Spring Cloud Gateway. It routes requests to the appropriate microservices based on predefined paths, integrates with Eureka for dynamic service discovery, and provides logging for monitoring and debugging purposes.

## User Interface

### Implementation Details
The user interface for MediSync is built using React for the web application and Flutter for the mobile application. These frameworks were chosen for their performance, scalability, and ease of use.

### API Testing Tools
API testing tools like Postman were used extensively to test and validate the APIs of each microservice. This ensured the reliability and correctness of the interactions between different services.

## Deployment

### Deployment Methods
MediSync can be deployed using the following methods:

#### Local Deployment
1. **Clone the Repositories:** Clone all the related repositories.
2. **Set Up Environment Variables:** Configure the necessary environment variables.
3. **Start Services:** Use terminal commands to start each microservice.

#### Docker Deployment
1. **Build Docker Images:** Build Docker images for each microservice.
2. **Run Containers:** Use Docker Compose to run all the containers together.
3. **Monitor Services:** Use Docker logs and Docker Compose commands to monitor the services.

### Development Challenges

During the development of MediSync, several challenges were encountered:

- **Data Privacy and Security:** Handling sensitive health data required implementing stringent security measures.
- **Service Interactions:** Ensuring reliable inter-service communication and data consistency.
- **Scalability:** Designing the system to handle a high number of concurrent users.
