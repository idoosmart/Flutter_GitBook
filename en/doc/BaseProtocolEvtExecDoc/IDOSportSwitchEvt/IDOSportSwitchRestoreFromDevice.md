#### Device Sends Command to Resume Exercise Data Exchange


**JSON Field Received by App**:

| Field Name | Field Type | Field Description   |
| ---------- | ---------- | -------------------- |
| day        | int        | Resume time: day     |
| hour       | int        | Resume time: hour    |
| minute     | int        | Resume time: minute  |
| second     | int        | Resume time: second  |

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
