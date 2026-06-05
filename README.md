# Hospital-Management-System

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


## System Architecture

```text
HospitalManagementSystem
│── models
│── interfaces
│── services
│── data
│── utils
└── main.cpp

Class Hierarchy

├── User
│   ├── Patient
│   ├── Doctor
│   ├── Receptionist
│   └── LabTechnician
│
├── Visit
│   ├── ScheduledVisit
│   ├── WalkInVisit
│   └── EmergencyVisit
│
├── Payment
│   ├── CashPayment
│   ├── CreditCardPayment
│   └── InsurancePayment
│
├── MedicalRecord
├── LabTest
├── Bill
├── Department
│
├── FileManager
└── Validator
```


## Technical Skills Demonstrated
- Object-oriented Programming (OOP)
- Inheritance and Polymorphism
- Dynamic Memory Management
- File I/O and CSV Persistence
- Data Modeling
- Software Architecture Design
- Input Validation
- Error Handling
- Business Workflow Modeling
- Git and Version Control


## Feature Enhancements (optional)
- MySQL adtabase integration
- User authentication
- GUI implementation
- REST Application Programming Interface (API) backend
- Cloud deployment
- Data analytics dashboard