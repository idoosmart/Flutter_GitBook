#### App Notifies the Device About the Data Exchange Pause


**JSON Field Received by App**:

| Field Name | Field Type | Field Description  |
| ---------- | ---------- | ----------------- |
| day        | int        | Resume time: day  |
| hour       | int        | Resume time: hour |
| minute     | int        | Resume time: minute    |
| second     | int        | Resume time: second    |

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 56,
    "second": 15
}
```
**JSON Field Sent by App**:

| Field Name | Field Type | Field Description                                      |
| ---------- | ---------- | ----------------------------------------------------- |
| err_code   | int        | err_code<br />0: Success<br />1: Failed: Not in exercise mode          |

`Example:`

```json
{
    "err_code": 0
}
```
