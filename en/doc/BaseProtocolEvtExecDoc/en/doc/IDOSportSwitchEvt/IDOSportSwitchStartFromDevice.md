#### Device Sends Command to Start Exercise Data Exchange


**JSON Field Received by App**:

| Field Name | Field Type | Field Description            |
| ---------- | ---------- | --------------------------- |
| day        | int        | Start time: day              |
| hour       | int        | Start time: hour             |
| minute     | int        | Start time: minute           |
| second     | int        | Start time: second           |
| type       | int        | Type of exercise             |
| operate    | int        | 1: Request app to enable GPS<br />2: Initiate exercise request |

`Example:`

```json
{
    "day": 26,
    "hour": 11,
    "minute": 2,
    "second": 50,
    "type": 1,
    "operate": 2
}
```

**JSON Field Sent by App**:

| Field Name | Field Type | Field Description            |
| ---------- | ---------- | --------------------------- |
| ret_code   | int        | 0: Success; 1: Failed        |
| operate    | int        | 1: Request app to enable GPS<br />2: Initiate exercise request |

`Example:`

```json
{
    "ret_code": 0,
    "operate": 2
}
```
