#### Device Sends Command to Exchange Exercise Data Completion


**JSON Field Received by App**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| day        | int        | End time: day     |
| hour       | int        | End time: hour    |
| minute     | int        | End time: minute  |
| second     | int        | End time: second  |

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

| Field Name | Field Type | Field Description                                        |
| ---------- | ---------- | ------------------------------------------------------- |
| ret_code   | int        | 0: Success<br />1: Failed: Device not in exercise mode |

`Example:`

```json
{
    "ret_code": 0
}
```

