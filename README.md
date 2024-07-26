# MediSync

MediSync is an AI-powered healthcare platform that integrates symptom analysis, disease prediction, doctor recommendations, and patient management. This project leverages a microservices architecture to provide a centralized solution for individuals seeking medical guidance and healthcare professionals overseeing patient care.

## Table of Contents

- [Introduction](#introduction)
- [Problem Definition](#problem-definition)
- [Proposed Solution](#proposed-solution)
- [Product Overview](#product-overview)
- [Key Features](#key-features)
- [API Endpoints](#api-endpoints)
- [Technical Architecture](#technical-architecture)
- [Implementation Plan](#implementation-plan)
- [Business Model](#business-model)
- [Marketing Plan](#marketing-plan)
- [Project Timeline](#project-timeline)
- [Team Members](#team-members)
- [Contact Information](#contact-information)

## Introduction

MediSync is a comprehensive healthcare assistance platform that seamlessly integrates AI-powered symptom analysis, disease prediction, doctor recommendations, patient management, and educational resources. Built on a microservices architecture, it offers a centralized solution for both individuals seeking medical guidance and healthcare professionals overseeing patient care.

## Problem Definition

In the healthcare field, getting timely and accurate medical help is vital, especially in remote areas where resources are limited. Patients often struggle to understand their symptoms correctly, which delays them from getting the right care they need. Finding the right healthcare providers quickly is also a challenge, making the situation even more urgent. Additionally, managing medical histories and treatment plans is tough, making it hard for patients and doctors to communicate well and causing problems in how healthcare is delivered.

## Proposed Solution

MediSync aims to tackle these challenges head-on. By using AI technology and a flexible microservices architecture, MediSync aims to break down the usual barriers to accessing healthcare. It does this by offering various services like analyzing symptoms, predicting diseases, helping patients find the right doctors, managing patient records, and providing educational materials. With MediSync, we want to make healthcare more accessible, efficient, and tailored to each person's needs.

## Related Repositories

- [Backend repo - MediSync_services](https://github.com/ChamaliVishmani/MediSync_services)
- [Frontend repo - MediSync-React-Frontend](https://github.com/Nilupa-Illangarathna/MediSync-React-Frontend)
- [ML repo - medisync_ml_backend](https://github.com/AsgardiansCode/medisync_ml_backend)
- [Discovery Server](https://github.com/AsgardiansCode/springboot-eureka-server)
- [API Gateway](https://github.com/ChamaliVishmani/Medisync-api-gateway)


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

### Microservices

- **Drug Interaction Checker Service:** Handles drug interaction checks.
- **Disease Prediction Service:** Utilizes AI to predict diseases based on symptoms.
- **Appointment Scheduling Service:** Manages doctor appointments and scheduling.
- **Symptom Analysis Service:** Uses NLP and AI to analyze and clarify symptoms.
- **Patient Health Log Service:** Provides interfaces for logging health metrics, medications, and treatment adherence.

### Supporting Infrastructure

- **Eureka Server:** Service discovery and registration.
- **API Gateway:** Central entry point for routing requests to various microservices.
- **Database:** Supabase and Firebase for data storage and management.
- **Cloud Provider:** AWS for robust and scalable infrastructure.
- **AI/ML Models:** TensorFlow, LangChain, LlamaIndex for AI functionalities.

## Implementation Plan

### Development Phase

- Finalize system design and architecture.
- Develop core features and machine learning models.
- Conduct testing and initial rollout to selected users.

### Launch Phase

- Full launch of the platform.
- Implement marketing campaigns and develop partnerships.
- Collect feedback and improve the platform.

### Expansion Phase

- Integrate with partner hospitals.
- Expand to new markets and introduce additional services.
- Continuously improve and develop new features.

## Business Model

### Revenue Generation Strategy

- **Subscription Fees:** Premium subscribers pay a recurring fee for advanced features.
- **Transaction Fees:** Revenue from doctor consultations and medication purchases.
- **Partnership Agreements:** Referral commissions from healthcare providers and pharmacies.
- **Advertising Revenue:** Targeted advertising placements on the platform.

### Cost Structure

- **Software Development:** Initial development and ongoing maintenance.
- **Employee Salaries:** For software developers and medical experts.
- **Hosting and Infrastructure:** Expenses for hosting and scalability.
- **Marketing and Advertising:** Budget for digital advertising and content creation.
- **Regulatory Compliance:** Costs for ensuring compliance with healthcare regulations.

## Marketing Plan

### Strategies

- **Digital Marketing:** Online advertising platforms like Google Ads and social media.
- **Content Marketing:** Informative blog posts, videos, and infographics.
- **Search Engine Optimization (SEO):** Optimizing the platform's website for relevant keywords.
- **Partnerships:** Collaborations with healthcare facilities and wellness organizations.
- **Influencer Marketing:** Collaborations with healthcare professionals and medical experts.
- **Events and Workshops:** Organizing virtual or in-person events on healthcare topics.

## Project Timeline

- **Project Planning and Design:** March 16, 2024 - March 24, 2024
- **Setup and Initial Development:** March 24, 2024 - March 31, 2024
- **AI/ML Creation:** March 24, 2024 - May 4, 2024
- **Mobile Application Development:** April 1, 2024 - April 30, 2024
- **Web Application Development:** April 1, 2024 - April 30, 2024
- **Backend Development:** March 29, 2024 - April 30, 2024
- **Integrations:** May 1, 2024 - May 5, 2024
- **Testing:** May 6, 2024 - May 10, 2024

## Team Members

### Thimira Nirmal
- **Role:** ML Engineer
- **Skills:** Python, C++, TensorFlow, PyTorch, LangChain, OpenAI, React, FastAPI
- **Experience:** ML Intern at LSEG, 4+ years of freelancing in ML and web development
- **Contact:** [timnirmal@gmail.com](mailto:timnirmal@gmail.com), [LinkedIn](https://www.linkedin.com/in/thimiranirmal/), [GitHub](https://github.com/timnirmal)

### Nilupa Lakshantha Illangarathna
- **Role:** Software Developer
- **Skills:** C++, JavaScript, Java, Python, Dart, Flutter SDK, React, Node.js
- **Experience:** Computer Engineering Intern at LSEG, Freelancer Software Developer
- **Contact:** [nilupalakshantha50@gmail.com](mailto:nilupalakshantha50@gmail.com), [LinkedIn](https://www.linkedin.com/in/nilupa-illangarathna-1a5a0720b/), [GitHub](https://github.com/Nilupa-Illangarathna)

### Chamali Vishmani
- **Role:** Software Engineering Intern
- **Skills:** Python, C++, JavaScript, React, Vue.js, Node.js, Django, MongoDB
- **Experience:** Software Engineering Intern at WSO2
- **Contact:** [chamali.vishmani@gmail.com](mailto:chamali.vishmani@gmail.com), [LinkedIn](https://www.linkedin.com/in/chamali-vishmani/), [GitHub](https://github.com/ChamaliVishmani)

## Contact Information

For more information about MediSync, please contact:

- **Project Team:** [medisync.team@example.com](mailto:medisync.team@example.com)
- **Website:** [medisync.com](http://medisync.com)

---
