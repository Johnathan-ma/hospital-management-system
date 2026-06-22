# State Diagram Notes

## Object

Appointment

## States

- Created
- Scheduled
- Rescheduled
- Cancelled
- Completed
- No-Show

## State Transitions

- Created -> Scheduled: appointment confirmed
- Scheduled -> Cancelled: appointment cancelled
- Scheduled -> Rescheduled: appointment date or time changed
- Rescheduled -> Scheduled: new appointment time confirmed
- Scheduled -> Completed: patient attends appointment
- Scheduled -> No-Show: patient does not attend appointment

## Final States

- Cancelled
- Completed
- No-Show