# Hospital-Management-System


## Table of Contents

- Overview
- Features
- Development Process
- Project Structure
- Getting Started
- Build Instructions
- Documentation
- System Architecture
- Class Hierarchy
- Technical Skills Demonstrated
- Future Enhancements


## Overview

A comprehensive hospital service management platform built in modern C++ that simulates real-world healthcare operations and administrative workflows.

The system provides role-based access for patients, receptionists, doctors, laboratory technicians, and administrators, enabling efficient management of:
- Patient registration and profile management
- Appointment scheduling and cancellation
- Walk-in and emergency visit handling
- Medical record management
- Laboratory test requests and result tracking
- Prescription management
- Billing and invoice generation
- Multiple payment methods (Cash, Credit Card, Insurance)
- Data persistence through CSV-based storage

The project follows object-oriented design principles and demonstrates:
- Encapsulation
- Inheritance
- Polymorphism
- Dynamic memory management
- File handling
- Modular software architecture
- Separation of concerns

The goal of this project is to bridge academic programming concepts with real-world healthcare management systems while serving as a foundation for future enterprise software development.


## Features

Patient Management
- Register new patients
- Update patient information
- View medical history
- Appointment tracking

Appointment System
- Schedule appointments
- Cancel appointments
- Walk-in visits
- Emergency visits

Medical Services
- Diagnosis records
- Prescription management
- Laboratory test requests
- Laboratory result tracking

Billing System
- Invoice generation
- Payment tracking
- Insurance claims
- Multiple payment methods

Administration
- Department management
- Doctor management
- System reporting
- Data persistence


## Development Process

This project follows a structured software development lifecycle inspired by system analysis and software engineering principles.

1. Requirements Analysis
2. System Design
3. Class Design
4. Data Design
5. Process Design
6. Implementation
7. Testing and Debugging

### Requirements Analysis

Define functional and non-functional requirements, user stories, and use cases.

### System Design

Design the overall architecture, modules, and folder structure.

### Class Design

Create UML class diagrams and define object relationships.

### Data Design

Design CSV schemas and create a data dictionary.

### Process Design

Model workflows using activity, swimlane, and state diagrams.

### Implementation

Develop the application using C++ and object-oriented principles.

### Testing and Debugging

Perform functional, boundary, and integration testing.

PS: Detailed documentation can be found in the `/docs` directory.


## Project Structure

```text
HospitalManagementSystem/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── requirements.md
│   ├── architecture.md
│   ├── csv-design.md
│   ├── data-dictionary.md
│   ├── testing-plan.md
│   ├── user-stories.md
│   ├── use-cases.md
│   │
│   └── diagrams/
│       ├── use-case-diagram.png
│       ├── architecture-diagram.png
│       ├── class-diagram.png
│       ├── activity-diagram.png
│       ├── swimlane-diagram.png
│       ├── state-diagram.png
│       └── er-diagram.png
│
├── data/
│   ├── patients.csv
│   ├── staff.csv
│   ├── departments.csv
│   ├── visits.csv
│   ├── medical_records.csv
│   ├── lab_tests.csv
│   ├── bills.csv
│   └── payments.csv
│
├── include/
│   ├── models/
│   ├── interfaces/
│   ├── services/
│   └── utils/
│
├── src/
│   ├── models/
│   ├── interfaces/
│   ├── services/
│   └── utils/
│
├── tests/
│   ├── test_patient.cpp
│   ├── test_appointment.cpp
│   ├── test_payment.cpp
│   └── test_file_manager.cpp
│
└── main.cpp
```


## Getting Started

This project is currently under development. The system is designed as a console-based C++ application with CSV-based persistence.

To run the project, clone the repository and open it in Visual Studio.


## Build Instructions

Build instructions will be updated as the implementation progresses.

Planned build options:
- Visual Studio 2026
- g++ command-line compilation


## Documentation

The complete project documentation is available in the `/docs` directory.

| Document | Description |
|----------|-------------|
| requirements.md | Functional and non-functional requirements |
| user-stories.md | User goals and scenarios |
| use-cases.md | Detailed use case descriptions |
| architecture.md | System architecture and module responsibilities |
| csv-design.md | CSV file schemas and relationships |
| data-dictionary.md | Field definitions and metadata |
| testing-plan.md | Test cases and validation strategy |
| use-case-diagram.png | User interactions and system functionality |
| architecture-diagram.png | High-level system architecture |
| class-diagram.png | UML class relationships |
| activity-diagram.png | Workflow processes |
| swimlane-diagram.png | Role responsibilities across workflows |
| state-diagram.png | Entity state transitions |
| er-diagram.png | Data relationships and entity mapping |


## System Architecture

This project follows a layered architecture to separate user interaction, business logic, object models, and data persistence.

```text
Hospital Management System

┌──────────────────────────────┐
│        Interface Layer        │
│PatientInterface              │
│ReceptionistInterface         │
│DoctorInterface               │
│LabInterface                  │
│AdminInterface                │
└───────────────↓──────────────┘

┌──────────────────────────────┐
│      Business Service Layer   │
│ PatientService               │
│ AppointmentService           │
│ MedicalRecordService         │
│ LabService                   │
│ BillingService               │
│ PaymentService               │
└───────────────↓──────────────┘

┌──────────────────────────────┐
│          Model Layer          │
│ User, Patient, Staff         │
│ Visit, Bill, Payment         │
│ MedicalRecord, LabTest       │
│ Department                   │
└───────────────↓──────────────┘

┌──────────────────────────────┐
│       Data Access Layer       │
│ FileManager                  │
│ Validator                    │
└───────────────↓──────────────┘

┌──────────────────────────────┐
│          CSV Storage          │
│ patients.csv                 │
│ staff.csv                    │
│ departments.csv              │
│ visits.csv                   │
│ medical_records.csv          │
│ lab_tests.csv                │
│ bills.csv                    │
│ payments.csv                 │
└──────────────────────────────┘
```
The Interface Layer handles menus and user input.
The Business Service Layer manages application rules and workflows.
The Model Layer represents real-world hospital entities.
The Data Access Layer handles CSV file reading and writing.
The CSV Storage Layer provides persistent data storage across program executions.


``` markdown
## Class Hierarchy

```text
User
├── Patient
└── Staff
    ├── Doctor
    ├── Receptionist
    ├── LabTechnician
    └── Administrator

Visit
├── ScheduledVisit
├── WalkInVisit
└── EmergencyVisit

Payment
├── CashPayment
├── CreditCardPayment
└── InsurancePayment

MedicalRecord
├── Diagnosis
├── Prescription
└── LabTest

Utility
├── FileManager
├── Validator
└── DateTime

Core Entities
├── Department
├── Bill
└── Appointment
```


## Technical Skills Demonstrated

- Object-oriented Programming (OOP)
- Inheritance and Polymorphism
- Dynamic Memory Management
- File I/O and CSV Persistence
- Data Modelling
- Software Architecture Design
- Input Validation
- Error Handling
- Business Workflow Modelling
- Git and Version Control


## Future Enhancements
- MySQL database integration
- User authentication
- GUI implementation
- REST Application Programming Interface (API) backend
- Cloud deployment
- Data analytics dashboard