# Hospital Management System - CSV Design

---

## Document structure

1. Purpose
2. CSV Files Overview
3. Detailed CSV Schemas
4. Relationships Between CSV Files
5. Data Integrity Rules

---

## 1. Purpose

This document defines the CSV file structure used for persistent data storage in the Hospital Management System.

Each .csv file represents a major business entity and contains the information required to restore the system state when the application starts.

The .csv files are designed to simulate a relational database while maintaining compatibility with a console-based C++ application

---

## 2. CSV Files Overview

| CSV File | Purpose |
| -------- | ------- |
| patients.csv | store patient information |
| staff.csv | store staff information |
| departments.csv | store department information |
| appointments.csv | store appointment information |
| visits.csv | store visit information |
| medical_records.csv | store medical records |
| dignoses.csv | store dignosis records |
| prescriptions.csv | store prescription records |
| lab_tests.csv | store laboratory tests |
| bills.csv | store billing records |
| payments.csv | store payment records |

---

## 3. Detailed CSV Schemas

### 3.1 patients.csv - Patient

patient_id
first_name
last_name
date_of_birth
phone
email
address
emergency_contact

Example:
P0001, john, Smith, 1990-05-12, 6471112222, john@gmail.com, Toronto, Mary Smith

### 3.2 staff.csv - Doctor | Receptionist | LabTechnician | Administrator

staff_id
first_name
last_name
role
department_id
phone
email

Example:
S0001, Emily, Wong, Doctor, D001, 6473334444, emily@hospital.com

### 3.3 departments.csv

department_id
department_name
location

Example:
D001, Cardiology, Floor 2

### 3.4 appointments.csv - Appointment

appointment_id
patient_id
doctor_id
appointment_date
appointment_time
status

status:
scheduled
rescheduled
cancalled
completed
no-show

Example:
A0001, P0001, S0001, 2026-08-01, 09:00, Scheduled

### 3.5 visits.csv - Visit

visit_id
patient_id
doctor_id
visit_date
visit_type
status

visit_type:
scheduled
walk-in
emergency

Example:
V0001, P0001, S0001, 2026-08-01, Walk_in, Completed

### 3.6 medical_records.csv - MedicalRecord

record_id
patient_id
visit_id
doctor_id
notes

Example:
MR0001, P0001, V0001, S0001, Patient recovering well

### 3.7 disgnosis.csv - Diagnosis

disgnosis_id
record_id
disgnosis_name
disgnosis_description
disgnosis_date

Example:
DG0001, MR0001, Influenza, Seasonal flu, 2026-08-01

### 3.8 prescriptions.csv - Prescription

prescription_id
record_id
medication_name
dosage
frequency
duration

Example:
PR0001, MR0001, Tylenol, 500mg, Twice Daily, 7 Days

### 3.9 lab_tests.csv - LabTest

lab_test_id
visit_id
patient_id
doctor_id
test_type
status
result

status:
pending
in progress
completed

Example:
LT0001, V0001, P0001, S0001, Blood Test, Completed, Normal

### 3.10 bills.csv - Bill

bill_id
visit_id
patient_id
total_amount
status

status:
unpaid
partially paid
paid

Example:
B0001, V0001, P0001, 120.00, unpaid

### 3.11 payments.csv - Payment

payment_id
bill_id
payment_method
amount
payment_date

payment_method:
cash
credit card
insurance

Example:
PM0001, B0001, credit card, 120.00, 2026-08-01

---

## 4. Relationships Between CSV Files

| Parent | Child |
| ------ | ----- |
| Patient | Appointment |
| Patient | Visit |
| Visit | MedicalRecord |
| MedicalRecord | Diagnosis |
| MedicalRecord | Prescription |
| Visit | LabTest |
| Visit | Bill |
| Bill | Payment |

```text
Patient
 ├── Appointment
 └── Visit
       ├── MedicalRecord
       │      ├── Diagnosis
       │      └── Prescription
       ├── LabTest
       └── Bill
              └── Payment
```

---

## 5. Data Integrity Rules

1. Every patient must have a unique patient_id.
2. Every appointment must reference an existing patient.
3. Every visit must reference an existing doctor.
4. Every diagnosis must reference an existing medical record.
5. Every payment must reference an existing bill.
6. IDs cannot be duplicated.