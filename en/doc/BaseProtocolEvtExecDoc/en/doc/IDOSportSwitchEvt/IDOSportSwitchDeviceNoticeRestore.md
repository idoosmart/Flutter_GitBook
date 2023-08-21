#### App Notifies the Device About the Data Exchange Resumption


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
    "minute": 55,
    "second": 53
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

Textual content in Chinese should be translated into English, while the structure should remain unchanged.