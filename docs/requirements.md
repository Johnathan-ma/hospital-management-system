# Hospital Management System - Requirements

## 1. Project Purpose

The purpose of this project is to develop a console-based Hospital Management System in C++ that simulates basic hospital administrative and clinical workflows.

The system is designed to manage patients, staff, appointments, visits, medical records, lab tests, billing, and payments using object-oriented programming principles and CSV-based data persistence.

This project is created for PRG210 and is intended to demonstrate software design, modular programming, file handling, input validation, and business workflow modelling.

---

## 2. Project Scope

### 2.1 In Scope

The system will include the following major functions:

* Patient registration and profile management
* Staff management
* Appointment scheduling and cancellation
* Walk-in and emergency visit handling
* Medical record creation
* Diagnosis and prescription recording
* Laboratory test request and result tracking
* Bill generation
* Payment processing
* CSV-based data storage
* Role-based menu interfaces

### 2.2 Out of Scope

The following features will not be implemented in this version:

* Graphical User Interface
* Real online booking
* Real payment processing
* Real insurance claim verification
* MySQL database integration
* Cloud deployment
* User password encryption
* REST API backend
* Mobile application

---

## 3. User Roles

The system will support the following roles:

### 3.1 Patient

A patient can:

* Register personal information
* View appointment information
* View visit history
* View bills and payment status

### 3.2 Receptionist

A receptionist can:

* Register new patients
* Search patient records
* Schedule appointments
* Cancel appointments
* Create walk-in visits
* Create emergency visits

### 3.3 Doctor

A doctor can:

* View assigned visits
* Create diagnosis records
* Add prescriptions
* Request lab tests
* Update medical records

### 3.4 Lab Technician

A lab technician can:

* View lab test requests
* Update lab test status
* Enter lab test results

### 3.5 Administrator

An administrator can:

* Manage staff records
* Manage departments
* View system reports
* Maintain system data

---

## 4. Functional Requirements

### 4.1 Patient Management

FR-01: The system shall allow a receptionist to register a new patient.

FR-02: The system shall store patient information in a CSV file.

FR-03: The system shall allow users to search for a patient by patient ID.

FR-04: The system shall allow patient information to be updated.

FR-05: The system shall allow users to view a patient's visit history.

---

### 4.2 Staff Management

FR-06: The system shall store staff information including doctors, receptionists, lab technicians, and administrators.

FR-07: The system shall allow administrators to add new staff members.

FR-08: The system shall allow staff members to be linked to departments.

---

### 4.3 Appointment Management

FR-09: The system shall allow a receptionist to schedule an appointment for a patient.

FR-10: The system shall allow an appointment to be assigned to a doctor.

FR-11: The system shall allow appointment status to be updated.

FR-12: The system shall allow appointments to be cancelled.

FR-13: The system shall prevent invalid appointment dates or empty appointment information.

---

### 4.4 Visit Management

FR-14: The system shall support scheduled visits.

FR-15: The system shall support walk-in visits.

FR-16: The system shall support emergency visits.

FR-17: The system shall store visit information in a CSV file.

FR-18: The system shall link each visit to a patient and a doctor.

---

### 4.5 Medical Record Management

FR-19: The system shall allow doctors to create medical records for patient visits.

FR-20: The system shall allow doctors to record diagnosis information.

FR-21: The system shall allow doctors to add prescription information.

FR-22: The system shall link medical records to patients and visits.

---

### 4.6 Laboratory Test Management

FR-23: The system shall allow doctors to request lab tests.

FR-24: The system shall allow lab technicians to update lab test status.

FR-25: The system shall allow lab technicians to enter lab test results.

FR-26: The system shall store lab test information in a CSV file.

---

### 4.7 Billing Management

FR-27: The system shall generate bills for patient visits.

FR-28: The system shall calculate bill amounts based on visit type and services.

FR-29: The system shall store bill information in a CSV file.

FR-30: The system shall allow users to view unpaid and paid bills.

---

### 4.8 Payment Management

FR-31: The system shall support cash payment.

FR-32: The system shall support credit card payment.

FR-33: The system shall support insurance payment.

FR-34: The system shall update bill status after payment.

FR-35: The system shall store payment records in a CSV file.

---

### 4.9 Data Persistence

FR-36: The system shall save patient data to CSV files.

FR-37: The system shall load existing data when the program starts.

FR-38: The system shall update CSV files when records are added or modified.

FR-39: The system shall use unique IDs for major records.

---

### 4.10 Input Validation

FR-40: The system shall validate required input fields.

FR-41: The system shall reject invalid numeric input.

FR-42: The system shall reject invalid menu choices.

FR-43: The system shall prevent empty names, IDs, and required fields.

---

## 5. Non-Functional Requirements

### 5.1 Maintainability

NFR-01: The system shall use a modular project structure.

NFR-02: The system shall separate interface, service, model, and utility logic.

NFR-03: The system shall avoid placing all logic inside main.cpp.

---

### 5.2 Usability

NFR-04: The system shall provide clear console menus.

NFR-05: The system shall display meaningful error messages.

NFR-06: The system shall guide users through each operation step by step.

---

### 5.3 Reliability

NFR-07: The system shall prevent common input errors from crashing the program.

NFR-08: The system shall preserve data between program runs using CSV files.

NFR-09: The system shall handle missing or empty CSV files safely.

---

### 5.4 Extensibility

NFR-10: The system shall be designed so that future database integration is possible.

NFR-11: The system shall allow future GUI or REST API development.

NFR-12: The system shall allow additional payment methods to be added in the future.

---

### 5.5 Performance

NFR-13: The system shall respond to user menu actions within a reasonable time.

NFR-14: The system shall be suitable for small to medium-sized CSV datasets.

---

## 6. System Constraints

The project will follow these constraints:

* The system will be written in C++.
* The system will be console-based.
* The system will use CSV files for data storage.
* The system will not use a real database in this version.
* The system will not include a GUI in this version.
* The system will focus on object-oriented programming and file handling.
* The system will be developed within approximately one month.

---

## 7. Core Business Workflows

The system will focus on five core workflows:

1. Patient Registration
2. Appointment Scheduling
3. Doctor Visit and Medical Record Creation
4. Lab Test Request and Result Update
5. Billing and Payment Processing

---

## 8. Assumptions

The project assumes that:

* Each patient has a unique patient ID.
* Each staff member has a unique staff ID.
* Each appointment has a unique appointment ID.
* Each visit has a unique visit ID.
* Each bill has a unique bill ID.
* Each payment has a unique payment ID.
* A patient may have multiple appointments.
* A patient may have multiple visits.
* A doctor may handle multiple visits.
* A visit may generate one medical record.
* A visit may generate one bill.
* A bill may be paid using one payment method.

---

## 9. Success Criteria

The project will be considered successful if:

* The system can register and store patients.
* The system can schedule and manage appointments.
* The system can create visits and medical records.
* The system can request and update lab tests.
* The system can generate bills and process payments.
* The system can save and load data using CSV files.
* The code is organized into models, services, interfaces, and utilities.
* The project demonstrates object-oriented programming concepts.
