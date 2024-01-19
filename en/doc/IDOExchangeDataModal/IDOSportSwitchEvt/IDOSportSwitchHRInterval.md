#### App Sends Request to Get Five Heart Rate Zones


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
    "minute": 56,
    "second": 15
}
```

**JSON Field Received by App**:

| Field Name | Field Type | Field Description               |
| ---------- | ---------- | ------------------------------ |
| range1     | int        | Heart rate value for zone 1     |
| range2     | int        | Heart rate value for zone 2     |
| range3     | int        | Heart rate value for zone 3     |
| range4     | int        | Heart rate value for zone 4     |
| range5     | int        | Heart rate value for zone 5     |

`Example:`

```json
{
    "range1": 0,
    "range2": 0,
    "range3": 56,
    "range4": 0,
    "range5": 0
}
```
