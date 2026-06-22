# Swimlane Activity Diagram Notes

## Selected Workflow

Schedule Appointment

## Purpose

This swimlane activity diagram shows the responsibilities of the Receptionist, System, Patient Data, and Staff/Appointment Data during the appointment scheduling process.

## Swimlanes

1. Receptionist
2. System
3. Patient Data
4. Staff / Appointment Data

## Workflow

1. Receptionist selects "Schedule Appointment".
2. System asks for patient ID.
3. Receptionist enters patient ID.
4. System validates the patient ID.
5. System reads `patients.csv`.
6. Patient Data returns whether the patient exists.
7. If the patient does not exist, System displays an error message and asks for patient ID again.
8. If the patient exists, System asks for doctor ID.
9. Receptionist enters doctor ID.
10. System validates the doctor ID.
11. System reads `staff.csv`.
12. Staff Data returns whether the doctor exists.
13. If the doctor does not exist, System displays an error message and asks for doctor ID again.
14. If the doctor exists, System asks for appointment date and time.
15. Receptionist enters appointment date and time.
16. System validates date and time.
17. If the date or time is invalid, System displays an error message and asks for date and time again.
18. If the date and time are valid, System generates an appointment ID.
19. System writes the new appointment to `appointments.csv`.
20. System displays a confirmation message.
21. Receptionist receives the confirmation.
22. End.