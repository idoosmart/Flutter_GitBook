#### App Sends Command to Pause Exercise Data Exchange


**JSON Field Sent by App**:

| Field Name       | Field Type | Field Description     |
| ---------------- | ---------- | --------------------- |
| day              | int        | Start time: day       |
| hour             | int        | Start time: hour      |
| minute           | int        | Start time: minute    |
| second           | int        | Start time: second    |
| sport_hour       | int        | Duration: hours       |
| sport_minute     | int        | Duration: minutes     |
| sport_second     | int        | Duration: seconds     |

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 54,
    "second": 50,
    "sport_hour": 10,
    "sport_minute": 54,
    "sport_second": 50
}
```

**JSON Field Received by App**:

| Field Name | Field Type | Field Description                                                        |
| ---------- | ---------- | ----------------------------------------------------------------------- |
| err_code   | int        | err_code<br/>0: Success<br/>1: Failed to enter exercise mode successfully |

`Example:`

```json
{
    "err_code": 0
}
```
