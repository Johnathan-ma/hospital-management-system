# Class Diagram Notes

## 1. Inheritance Relationships

### User Hierarchy

User is the base class for all system users.

* Patient inherits from User.
* Staff inherits from User.
* Doctor inherits from Staff.
* Receptionist inherits from Staff.
* LabTechnician inherits from Staff.
* Administrator inherits from Staff.

### Visit Hierarchy

Visit is the base class for all visit types.

* ScheduledVisit inherits from Visit.
* WalkInVisit inherits from Visit.
* EmergencyVisit inherits from Visit.

### Payment Hierarchy

Payment is the base class for all payment types.

* CashPayment inherits from Payment.
* CreditCardPayment inherits from Payment.
* InsurancePayment inherits from Payment.

---

## 2. Main Classes

### User

Attributes:

* userId
* firstName
* lastName
* phone
* email

Methods:

* getUserId()
* getFullName()
* displayInfo()

---

### Patient

Attributes:

* patientId
* dateOfBirth
* address
* emergencyContact

Methods:

* displayPatientInfo()
* updatePatientInfo()

---

### Staff

Attributes:

* staffId
* departmentId
* role

Methods:

* displayStaffInfo()

---

### Doctor

Attributes:

* specialization
* licenseNumber

Methods:

* viewAssignedVisits()
* createMedicalRecord()
* requestLabTest()

---

### Receptionist

Methods:

* registerPatient()
* scheduleAppointment()
* cancelAppointment()
* createWalkInVisit()
* createEmergencyVisit()
* generateBill()
* processPayment()

---

### LabTechnician

Methods:

* viewLabTestRequests()
* updateLabTestStatus()
* enterLabTestResult()

---

### Administrator

Methods:

* manageStaff()
* manageDepartment()
* viewReports()

---

### Appointment

Attributes:

* appointmentId
* patientId
* doctorId
* appointmentDate
* appointmentTime
* status

Methods:

* schedule()
* reschedule()
* cancel()
* markCompleted()
* markNoShow()

---

### Visit

Attributes:

* visitId
* patientId
* doctorId
* visitDate
* visitType
* status

Methods:

* startVisit()
* completeVisit()
* displayVisitInfo()

---

### MedicalRecord

Attributes:

* recordId
* patientId
* visitId
* doctorId
* diagnosis
* prescription
* notes

Methods:

* addDiagnosis()
* addPrescription()
* updateNotes()

---

### LabTest

Attributes:

* labTestId
* patientId
* visitId
* testType
* status
* result

Methods:

* updateStatus()
* enterResult()

---

### Bill

Attributes:

* billId
* patientId
* visitId
* totalAmount
* status

Methods:

* calculateTotal()
* markPaid()
* displayBill()

---

### Payment

Attributes:

* paymentId
* billId
* amount
* paymentDate
* paymentMethod

Methods:

* processPayment()
* displayPaymentInfo()

---

### Department

Attributes:

* departmentId
* departmentName
* location

Methods:

* displayDepartmentInfo()

---

### FileManager

Methods:

* loadPatients()
* savePatients()
* loadAppointments()
* saveAppointments()
* loadVisits()
* saveVisits()
* loadBills()
* saveBills()
* loadPayments()
* savePayments()

---

### Validator

Methods:

* validateNonEmpty()
* validateNumber()
* validateDate()
* validateMenuChoice()

---

### IDGenerator

Methods:

* generatePatientId()
* generateAppointmentId()
* generateVisitId()
* generateBillId()
* generatePaymentId()
