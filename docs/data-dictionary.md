# Hospital Management System - Data Dictionary

---

## Field Dictionary

* patients.csv
* staff.csv
* departments.csv
* appointments.csv
* visits.csv
* medical_records.csv
* diagnosis.csv
* prescriptions.csv
* lab_tests.csv
* bills.csv
* payments.csv

### patients.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| first_name | string | yes | patient first name | cannot be empty | Johnathan |
| last_name | string | yes | patient last name | cannot be empty | Smith |
| date_of_birth | date | yes | patient date of birth | format: YYYY-MM-DD | 1989-05-01 |
| phone | string | yes | patient phone number | digits only, 10 characters recommended | 2269618291 |
| email | string | no | patient email address | should contain @ if provided | john@hotmail.com |
| address | string | yes | patient home address | cannot be empty | Toronto |
| emergency_contact | string | yes | Emergency contact name or phone | cannot be empty | Susan Smith |

### staff.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| staff_id | string | yes | unique staff identifier | must start with S and contain 4 digits | S0001 |
| first_name | string | yes | staff first name | cannot be empty | Emily |
| last_name | string | yes | staff last name | cannot be empty | Antonio |
| role | string | yes | staff occupation | Doctor, Receptionist, LabTechnician, Administrator | Doctor |
| department_id | string | yes | unique department identifier | must start with D and contain 3 digits | D001 |
| phone | string | yes | staff phone number | digits only, 10 characters recommended | 5199926427 |
| email | string | no | staff email address | should contain @ if provided | emily@hospital.com |

### departments.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| department_id | string | yes | unique department identifier | must start with D and contain 3 digits | D001 |
| department_name | string | yes | department full name | cannot be empty | Cardiology |
| location | string | yes | a department's location, usually stands for an entire floor or section in hospital | cannot be empty | Floor 2 Section A |

### appointments.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| appointment_id | string | yes | unique appointment identifier | must start with A and contain 4 digits | A0001 |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| doctor_id | string | yes | unique staff identifier. Starts with S as it belongs to staff | must start with S and contain 4 digits | S0001 |
| appointment_date | date | yes | patient making appointment date | format: YYYY-MM-DD | 2025-12-17 |
| appointment_time | time_t | yes | patient visit time | format: HH:MM, 24-hour format, hour must be 00-23 and minute must be 00-59 | 09:30 |
| status | enum | yes | patient appointment status | choose one of five: "Scheduled", "Rescheduled", "Cancelled", "Completed", "No-show" | Completed |

### visits.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| visit_id | string | yes | unique visit identifier | must start with V and contain 4 digits | V0001 |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| doctor_id | string | yes | unique staff identifier. Starts with S as it belongs to staff | must start with S and contain 4 digits | S0001 |
| visit_date | date | yes | patient visiting date | format: YYYY-MM-DD | 2025-12-18 |
| visit_type | enum | yes | patient visit type | choose one of three: "Scheduled", "Walk-in", "Emergency" | Scheduled |
| status | enum | yes | patient visit status | choose one of three: "Active", "Completed", "Cancelled" | Completed |

### medical_records.csv

| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| record_id | string | yes | unique record identifier | must start with MR and contain 4 digits | MR0001 |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| visit_id | string | yes | unique visit identifier | must start with V and contain 4 digits | V0001 |
| doctor_id | string | yes | unique staff identifier. Starts with S as it belongs to staff | must start with S and contain 4 digits | S0001 |
| notes | string | no | medical record notes as a reminder | Optional text field, can be empty | Patient Mary is taking an injection for curing the fever. |

### diagnoses.csv
| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| diagnosis_id | string | yes | unique diagnosis identifier | must start with DG and contain 4 digits | DG0001 |
| record_id | string | yes | unique record identifier | must start with MR and contain 4 digits | MR0001 |
| diagnosis_name | string | yes | diagnosis name that patient takes | cannot be empty | Influenza |
| diagnosis_description | string | yes | diagnosis describing contents | cannot be empty | Seasonal flu |
| diagnosis_date | date | yes | date of diagnosis | cannot be empty | YYYY-MM-DD |

### prescriptions.csv
| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| prescription_id | string | yes | unique prescription identifier | must start with PR and contain 4 digits | PR0001 |
| record_id | string | yes | unique record identifier | must start with MR and contain 4 digits | MR0001 |
| medication_name | string | yes | medication name | cannot be empty | Tylenol |
| dosage | string | yes | dosage per treatment course | cannot be empty | 500mg |
| frequency | string | yes | frequency of dosage per treatment course | cannot be empty | Twice Daily |
| duration | string | yes | total dosage period | cannot be empty, can be 1-2 digit(s), space, and string | 7 Days |

### lab_tests.csv
| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| lab_test_id | string | yes | unique labTest identifier | must start with LT and contain 4 digits | LT0001 |
| visit_id | string | yes | unique visit identifier | must start with V and contain 4 digits | V0001 |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| doctor_id | string | yes | unique staff identifier. Starts with S as it belongs to staff | must start with S and contain 4 digits | S0001 |
| test_type | string | yes | test type patient takes | cannot be empty | Blood Test |
| status | enum | yes | lab test status | choose one of three: "Pending", "In Progress", "Completed" | Completed |
| result | string | no | lab test result | required only when status is Completed | Normal |

### bills.csv
| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| bill_id | string | yes | unique bill identifier | must start with B and contain 4 digits | B0001 |
| visit_id | string | yes | unique visit identifier | must start with V and contain 4 digits | V0001 |
| patient_id | string | yes | unique patient identifier | must start with P and contain 4 digits | P0001 |
| total_amount | double | yes | total amount of money on the bill | has to be greater than or equal to 0.00 | 120.00 |
| status | enum | yes | bill payment status | choose one of three: "Unpaid", "Partially Paid", "Paid" | Unpaid |

### payments.csv
| Field Name | Data Type | Required | Description | Validation Rule | Example |
| --- | --- | --- | --- | --- | --- |
| payment_id | string | yes | unique payment identifier | must start with PM and contain 4 digits| PM0001 |
| bill_id | string | yes | unique bill identifier | must start with B and contain 4 digits | B0001 |
| payment_method | enum | yes | payment method | choose one of three: "Cash", "Credit Card", "Insurance" | Insurance |
| amount | double | yes | the amount of payment that patient pays | has to be greater than or equal to 0.00 | 120.00 |
| payment_date | date | yes | payment date | format: YYYY-MM-DD | 2025-12-30 |

---

## Status Values

### Appointment Status
- Scheduled
- Rescheduled
- Cancelled
- Completed
- No-Show

### Visit Status
- Active
- Completed
- Cancelled

### Lab Test Status
- Pending
- In Progress
- Completed

### Bill Status
- Unpaid
- Partially Paid
- Paid

---

## ID Format Rules

P0001 = Patient
S0001 = Staff
D001 = Department
A0001 = Appointment
V0001 = Visit
MR0001 = Medical Record
DG0001 = Diagnosis
PR0001 = Prescription
LT0001 = Lab Test
B0001 = Bill
PM0001 = Payment

---

## Relationship / Foreign Key Rules

patient_id in appointments.csv must exist in patients.csv.
doctor_id in appointments.csv must exist in staff.csv and role must be Doctor.
visit_id in medical_records.csv must exist in visits.csv.
record_id in diagnoses.csv must exist in medical_records.csv.
record_id in prescriptions.csv must exist in medical_records.csv.
bill_id in payments.csv must exist in bills.csv.