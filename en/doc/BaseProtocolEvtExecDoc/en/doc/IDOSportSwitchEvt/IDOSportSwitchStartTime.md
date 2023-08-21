#### App Sends Start Time for Exercise Data Exchange


**JSON Field Sent by App**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ---------------- |
| day        | int        | Start time: day   |
| hour       | int        | Start time: hour  |
| minute     | int        | Start time: minute|
| second     | int        | Start time: second|

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 55,
    "second": 53
}
```

**JSON Field Received by App**:

| Field Name    | Field Type | Field Description   |
| ------------- | ---------- | --------------------|
| hour          | int        | Exercise time: hour |
| minute        | int        | Exercise time: minute|
| second        | int        | Exercise time: second|
| millisecond   | int        | TBD|

`Example:`

```json
{
    "hour": 10,
    "minute": 56,
    "millisecond": 0
}
```
