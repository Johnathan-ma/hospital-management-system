# Activity Diagram Notes

## Selected Workflow

Schedule Appointment

## Purpose

This activity diagram describes how a receptionist schedules an appointment for an existing patient with a doctor.

## Actor

Receptionist

## Main Flow

1. Start
2. Receptionist selects "Schedule Appointment"
3. System asks for patient ID
4. Receptionist enters patient ID
5. System searches patient record
6. If patient is not found, display error message and return to patient ID input
7. If patient is found, system asks for doctor ID
8. Receptionist enters doctor ID
9. System searches doctor record
10. If doctor is not found, display error message and return to doctor ID input
11. If doctor is found, system asks for appointment date and time
12. Receptionist enters appointment date and time
13. System validates date and time
14. If date or time is invalid, display error message and request input again
15. If valid, system generates appointment ID
16. System saves appointment to appointments.csv
17. System displays confirmation message
18. End

## Decision Points

- Patient found?
- Doctor found?
- Date and time valid?

## Data Used

- patients.csv
- staff.csv
- appointments.csv

## Related Use Case

UC-03: Schedule Appointment