# Use Case Diagram Notes

## Actors

* Patient
* Receptionist
* Doctor
* Lab Technician
* Administrator

## System Boundary

Hospital Management System

## Use Cases by Actor

### Patient

* View Appointment
* View Visit History
* View Lab Test Result
* View Bill Status

### Receptionist

* Register Patient
* Search Patient
* Update Patient
* Schedule Appointment
* Cancel Appointment
* Create Walk-In Visit
* Create Emergency Visit
* Generate Bill
* Process Payment

### Doctor

* View Assigned Visits
* View Patient History
* Create Medical Record
* Add Diagnosis
* Add Prescription
* Request Lab Test

### Lab Technician

* View Lab Test Requests
* Update Lab Test Status
* Enter Lab Test Result

### Administrator

* Manage Staff
* Manage Departments
* View Reports
* Maintain System Data

## Use Case Relationships (Include / Extend)

### Includes
- `Create Walk-In Visit` -> <<include>> -> `Search Patient`
- `Create Emergency Visit` -> <<include>> -> `Search Patient`
- `Create Medical Record` -> <<include>> -> `Add Diagnosis`
- `Generate Bill` -> <<include>> -> `Process Payment`

### Extends
- `Register Patient` -> <<extend>> -> `Search Patient` (Condition: Patient record not found)
- `Add Prescription` -> <<extend>> -> `Create Medical Record` (Condition: Medication required)
- `Request Lab Test` -> <<extend>> -> `Create Medical Record` (Condition: Diagnostic testing required)