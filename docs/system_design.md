Markdown

# Hospital Management System

## Project Overview

A modular console-based hospital management system developed in C++.

The system simulates real-world hospital workflows including:

- Patient registration
- Appointment scheduling
- Emergency visits
- Doctor consultations
- Lab testing
- Billing and payment processing

The project focuses on:

- Object-Oriented Programming
- Encapsulation
- Inheritance
- Polymorphism
- Dynamic memory management
- CSV-based data persistence
- Modular software architecture

---

# Core System Modules

## 1. Patient Management
Handles Patient registration and patient records.

## 2. Appointment System
Handles scheduled appointments and walk-in visits.

## 3. Emergency System
Handles emergency patient visits with priority handling.

## 4. Doctor System
Allows doctors to manage consultations and disgnoses.

## 5. Lab system
Handles lab test requests and lab results.

## 6. Billing and Payment system
Handles billing, insurance, and payment processing.

---

# User Roles

## Patient
- Book appointments
- View bills
- View lab results

## Receptionist
- Register patients
- Schedule appointments
- Generate bills

## Doctor
- View appointments
- Disgnose patients
- Request lab tests

## Lab Technician
- Process lab tests
- Enter lab results

## Admin
- Manage departments
- Manage doctors
- Save system data

---

# Planned Flder Structure

/models
/interfaces
/services
/utils
/data
/docs

---

# Planned CSV Files

patients.csv
appointments.csv
visits.csv
lab_tests.csv
bills.csv
payments.csv

---

# Planned Core Classes

## Models
- Patient
- Doctor
- Visit
- Appoitment
- Bill
- LabTest

## Interfaces
- MainInterface
- PatientInterface
- DoctorInterface
- AdminInterface

## Services
- AppointmentService
- BillingService
- Labservice

## Utilities
- Validator
- FileHelper
- UIHelper

---

# Future Improvements

- Database integration
- Authentication system
- GUI version
- Backend API integration
- Cloud deployment