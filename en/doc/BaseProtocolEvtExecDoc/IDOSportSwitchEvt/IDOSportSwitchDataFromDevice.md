#### Process of Exchanging Exercise Data with the Device


**JSON Field Received by App**:

| Field Name | Field Type | Field Description       |
| ---------- | ---------- | ---------------------- |
| day        | int        | Start time: day        |
| hour       | int        | Start time: hour       |
| minute     | int        | Start time: minute     |
| second     | int        | Start time: second     |
| distance   | int        | Distance in 0.01 km    |

`Example:`

```json
{
    "day": 26,
    "hour": 11,
    "minute": 3,
    "second": 15,
    "distance": 10
}
```

**JSON Field Sent by App**:

| Field Name | Field Type | Field Description                                                                                      |
| ---------- | ---------- | ----------------------------------------------------------------------------------------------------- |
| distance   | int        | Distance in 0.01 km.<br />The app needs to check if the distance is reasonable (based on GPS signal strength and common sense). |

`Example:`

```json
{
    "distance": 10
}
```

Textual content in Chinese should be translated into English, while the structure should remain unchanged.