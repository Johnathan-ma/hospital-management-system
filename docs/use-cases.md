# Hospital Management System - Use Cases

## 1. Introduction

This document describes the major use cases of the Hospital Management System.

A use case explains how a user interacts with the system to complete a specific goal. Each use case includes the actor, preconditions, main flow, alternative flow, and postconditions.

The system supports the following major actors:

* Patient
* Receptionist
* Doctor
* Lab Technician
* Administrator

---

## 2. Use Case List

| Use Case ID | Use Case Name          | Primary Actor  |
| ----------- | ---------------------- | -------------- |
| UC-01       | Register Patient       | Receptionist   |
| UC-02       | Search Patient         | Receptionist   |
| UC-03       | Schedule Appointment   | Receptionist   |
| UC-04       | Cancel Appointment     | Receptionist   |
| UC-05       | Create Walk-In Visit   | Receptionist   |
| UC-06       | Create Emergency Visit | Receptionist   |
| UC-07       | Create Medical Record  | Doctor         |
| UC-08       | Request Lab Test       | Doctor         |
| UC-09       | Update Lab Test Result | Lab Technician |
| UC-10       | Generate Bill          | Receptionist   |
| UC-11       | Process Payment        | Receptionist   |
| UC-12       | Manage Staff           | Administrator  |
| UC-13       | Manage Department      | Administrator  |

---

## 3. UC-01: Register Patient

### Primary Actor

Receptionist

### Goal

To register a new patient in the hospital system.

### Preconditions

* The system is running.
* The receptionist has selected the patient management menu.

### Main Flow

1. The receptionist selects "Register New Patient".
2. The system asks for patient information.
3. The receptionist enters the patient's name, date of birth, phone number, address, and other required information.
4. The system validates the input.
5. The system generates a unique patient ID.
6. The system stores the patient record in `patients.csv`.
7. The system displays a success message.

### Alternative Flow

* If required information is missing, the system displays an error message.
* If invalid input is entered, the system asks the receptionist to enter the information again.

### Postconditions

* A new patient record is created.
* The patient can be searched by patient ID.

---

## 4. UC-02: Search Patient

### Primary Actor

Receptionist

### Goal

To find an existing patient record.

### Preconditions

* At least one patient record exists in the system.

### Main Flow

1. The receptionist selects "Search Patient".
2. The system asks for a patient ID.
3. The receptionist enters the patient ID.
4. The system searches `patients.csv`.
5. The system displays the patient information if found.

### Alternative Flow

* If the patient ID does not exist, the system displays "Patient not found".
* If the input is empty, the system asks for the patient ID again.

### Postconditions

* The receptionist can view the patient's information.

---

## 5. UC-03: Schedule Appointment

### Primary Actor

Receptionist

### Goal

To schedule an appointment for a patient with a doctor.

### Preconditions

* The patient exists in the system.
* The doctor exists in the system.
* The appointment date and time are valid.

### Main Flow

1. The receptionist selects "Schedule Appointment".
2. The system asks for the patient ID.
3. The receptionist enters the patient ID.
4. The system checks whether the patient exists.
5. The system asks for the doctor ID.
6. The receptionist enters the doctor ID.
7. The system checks whether the doctor exists.
8. The receptionist enters the appointment date and time.
9. The system validates the appointment information.
10. The system generates a unique appointment ID.
11. The system saves the appointment to `appointments.csv`.
12. The system displays a confirmation message.

### Alternative Flow

* If the patient does not exist, the system displays an error message.
* If the doctor does not exist, the system displays an error message.
* If the date or time is invalid, the system asks for valid input again.

### Postconditions

* A new appointment is created.
* The appointment status is set to "Scheduled".

---

## 6. UC-04: Cancel Appointment

### Primary Actor

Receptionist

### Goal

To cancel an existing appointment.

### Preconditions

* The appointment exists.
* The appointment has not already been completed.

### Main Flow

1. The receptionist selects "Cancel Appointment".
2. The system asks for the appointment ID.
3. The receptionist enters the appointment ID.
4. The system searches for the appointment.
5. The system displays the appointment details.
6. The receptionist confirms cancellation.
7. The system updates the appointment status to "Cancelled".
8. The system saves the updated record.

### Alternative Flow

* If the appointment does not exist, the system displays an error message.
* If the appointment is already completed, the system does not allow cancellation.

### Postconditions

* The appointment status is updated to "Cancelled".

---

## 7. UC-05: Create Walk-In Visit

### Primary Actor

Receptionist

### Goal

To create a visit record for a patient without a prior appointment.

### Preconditions

* The patient exists in the system.
* A doctor is available.

### Main Flow

1. The receptionist selects "Create Walk-In Visit".
2. The system asks for the patient ID.
3. The receptionist enters the patient ID.
4. The system checks whether the patient exists.
5. The receptionist selects or enters the doctor ID.
6. The system generates a unique visit ID.
7. The system creates a visit with type "Walk-In".
8. The system saves the visit to `visits.csv`.

### Alternative Flow

* If the patient does not exist, the system asks the receptionist to register the patient first.
* If the doctor does not exist, the system displays an error message.

### Postconditions

* A walk-in visit record is created.

---

## 8. UC-06: Create Emergency Visit

### Primary Actor

Receptionist

### Goal

To create an emergency visit record for an urgent patient case.

### Preconditions

* The patient exists or can be registered quickly.
* Emergency visit type is selected.

### Main Flow

1. The receptionist selects "Create Emergency Visit".
2. The system asks for patient information or patient ID.
3. The receptionist enters the required information.
4. The system validates the input.
5. The system assigns the visit type as "Emergency".
6. The system generates a unique visit ID.
7. The system saves the emergency visit to `visits.csv`.
8. The system displays a success message.

### Alternative Flow

* If the patient is not registered, the receptionist registers the patient first.
* If required information is missing, the system asks for the information again.

### Postconditions

* An emergency visit record is created.

---

## 9. UC-07: Create Medical Record

### Primary Actor

Doctor

### Goal

To create a medical record for a patient visit.

### Preconditions

* A visit exists.
* The doctor is assigned to the visit.

### Main Flow

1. The doctor selects "Create Medical Record".
2. The system asks for the visit ID.
3. The doctor enters the visit ID.
4. The system verifies the visit.
5. The doctor enters diagnosis information.
6. The doctor enters treatment notes.
7. The doctor may enter prescription information.
8. The system generates a unique medical record ID.
9. The system saves the record to `medical_records.csv`.

### Alternative Flow

* If the visit does not exist, the system displays an error message.
* If required medical information is missing, the system asks the doctor to complete it.

### Postconditions

* A medical record is created and linked to the visit and patient.

---

## 10. UC-08: Request Lab Test

### Primary Actor

Doctor

### Goal

To request a laboratory test for a patient.

### Preconditions

* A patient visit exists.
* A medical record exists or is being created.

### Main Flow

1. The doctor selects "Request Lab Test".
2. The system asks for the patient ID or visit ID.
3. The doctor enters the required ID.
4. The system verifies the patient or visit.
5. The doctor enters the lab test type.
6. The doctor enters test notes if needed.
7. The system generates a unique lab test ID.
8. The system sets the lab test status to "Pending".
9. The system saves the lab test request to `lab_tests.csv`.

### Alternative Flow

* If the patient or visit does not exist, the system displays an error message.
* If the lab test type is empty, the system asks for valid input.

### Postconditions

* A lab test request is created.
* The lab test status is "Pending".

---

## 11. UC-09: Update Lab Test Result

### Primary Actor

Lab Technician

### Goal

To update the status and result of a laboratory test.

### Preconditions

* A lab test request exists.
* The lab test status is "Pending" or "In Progress".

### Main Flow

1. The lab technician selects "Update Lab Test Result".
2. The system asks for the lab test ID.
3. The lab technician enters the lab test ID.
4. The system searches for the lab test record.
5. The lab technician updates the test status.
6. The lab technician enters the test result.
7. The system saves the updated lab test record to `lab_tests.csv`.

### Alternative Flow

* If the lab test ID does not exist, the system displays an error message.
* If the result is empty, the system asks for valid input.

### Postconditions

* The lab test result is updated.
* The lab test status may become "Completed".

---

## 12. UC-10: Generate Bill

### Primary Actor

Receptionist

### Goal

To generate a bill for a patient visit.

### Preconditions

* A visit exists.
* The visit has not already been billed.

### Main Flow

1. The receptionist selects "Generate Bill".
2. The system asks for the visit ID.
3. The receptionist enters the visit ID.
4. The system verifies the visit.
5. The system calculates the bill amount based on visit type and services.
6. The system generates a unique bill ID.
7. The system sets the bill status to "Unpaid".
8. The system saves the bill to `bills.csv`.
9. The system displays the bill summary.

### Alternative Flow

* If the visit does not exist, the system displays an error message.
* If the bill already exists, the system displays the existing bill information.

### Postconditions

* A bill is created for the visit.
* The bill status is "Unpaid".

---

## 13. UC-11: Process Payment

### Primary Actor

Receptionist

### Goal

To process a payment for an unpaid bill.

### Preconditions

* A bill exists.
* The bill status is "Unpaid" or "Partially Paid".

### Main Flow

1. The receptionist selects "Process Payment".
2. The system asks for the bill ID.
3. The receptionist enters the bill ID.
4. The system displays bill information.
5. The receptionist selects a payment method.
6. The receptionist enters payment amount.
7. The system validates the payment amount.
8. The system generates a unique payment ID.
9. The system saves the payment to `payments.csv`.
10. The system updates the bill status.
11. The system displays a payment confirmation message.

### Alternative Flow

* If the bill does not exist, the system displays an error message.
* If the payment amount is invalid, the system asks for the amount again.
* If the bill is already paid, the system displays "Bill already paid".

### Postconditions

* A payment record is created.
* The bill status is updated to "Paid" or "Partially Paid".

---

## 14. UC-12: Manage Staff

### Primary Actor

Administrator

### Goal

To add, update, or view staff records.

### Preconditions

* The administrator has selected the staff management menu.

### Main Flow

1. The administrator selects "Manage Staff".
2. The system displays staff management options.
3. The administrator chooses to add, update, or view staff.
4. The system asks for required staff information.
5. The administrator enters staff details.
6. The system validates the input.
7. The system saves staff information to `staff.csv`.

### Alternative Flow

* If required information is missing, the system asks for valid input.
* If the staff ID does not exist during update, the system displays an error message.

### Postconditions

* Staff information is created, updated, or displayed.

---

## 15. UC-13: Manage Department

### Primary Actor

Administrator

### Goal

To manage hospital departments.

### Preconditions

* The administrator has selected the department management menu.

### Main Flow

1. The administrator selects "Manage Department".
2. The system displays department options.
3. The administrator chooses to add, update, or view departments.
4. The system asks for department information.
5. The administrator enters the required data.
6. The system validates the input.
7. The system saves department information to `departments.csv`.

### Alternative Flow

* If the department ID does not exist, the system displays an error message.
* If required fields are empty, the system asks for valid input.

### Postconditions

* Department information is created, updated, or displayed.

---

## 16. Relationship Between User Stories and Use Cases

| User Story ID | Related Use Case |
| ------------- | ---------------- |
| US-REC-01     | UC-01            |
| US-REC-02     | UC-02            |
| US-REC-04     | UC-03            |
| US-REC-05     | UC-04            |
| US-REC-06     | UC-05            |
| US-REC-07     | UC-06            |
| US-DOC-03     | UC-07            |
| US-DOC-05     | UC-08            |
| US-LAB-03     | UC-09            |
| US-REC-08     | UC-10            |
| US-REC-09     | UC-11            |
| US-ADM-01     | UC-12            |
| US-ADM-02     | UC-13            |

---

## 17. Notes for Implementation

These use cases will guide the design of:

* Interface classes
* Service classes
* Model classes
* CSV file schemas
* Activity diagrams
* Swimlane diagrams
* Test cases

Each use case should eventually map to one or more service functions in the C++ implementation.
