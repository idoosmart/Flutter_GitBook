#### Device Sends Command to Pause Exercise Data Exchange


**JSON Field Received by App**:

| Field Name | Field Type | Field Description   |
| ---------- | ---------- | -------------------- |
| day        | int        | Pause time: day      |
| hour       | int        | Pause time: hour     |
| minute     | int        | Pause time: minute   |
| second     | int        | Pause time: second   |

`Example:`

```json
{
    "day": 26,
    "hour": 11,
    "minute": 3,
    "second": 15
}
```

**JSON Field Sent by App**:

| Field Name | Field Type | Field Description                                                     |
| ---------- | ---------- | -------------------------------------------------------------------- |
| ret_code   | int        | ret_code<br/>0: Success<br/>1: Failed to enter exercise mode successfully |

`Example:`

```json
{
    "ret_code": 0
}
```
