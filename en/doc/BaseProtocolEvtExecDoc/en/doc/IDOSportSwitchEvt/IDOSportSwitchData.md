#### Process of Exchanging Exercise Data with the App


**JSON Field Sent by App**:

| Field Name   | Field Type | Field Description                                        |
| ------------ | ---------- | ------------------------------------------------------- |
| day          | int        | Start time: day                                          |
| hour         | int        | Start time: hour                                         |
| minute       | int        | Start time: minute                                       |
| second       | int        | Start time: second                                       |
| duration     | int        | Duration in seconds                                      |
| calories     | int        | Calories in kilocalories                                |
| distance     | int        | Distance in 0.01 km                                     |
| status       | int        | 0: All valid<br />1: Invalid distance<br />2: Weak GPS signal |

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 46,
    "second": 30,
    "duration": 80,
    "calories": 300,
    "distance": 500,
    "status": 0
}
```

**JSON Field Received by App**:

| Field Name       | Field Type | Field Description                                       |
| ---------------- | ---------- | ------------------------------------------------------ |
| status           | int        | 1: Success<br />2: Failed: Device not in exercise mode |
| step             | int        | Step/Count                                              |
| calories         | int        | Calories in kilocalories                               |
| distance         | int        | Distance in 0.01 km                                     |
| cur_hr_value     | int        | Heart rate data: Current heart rate                     |
| interval_second  | int        | Heart rate interval in seconds                          |
| hr_value_serial  | int        | Serial number                                           |
| hr_value         | int[]      | Heart rate value data                                   |

`Example:`

```json
{
    "status": 1,
    "step": 200,
    "calories": 200,
    "distance": 50,
    "cur_hr_value": 80,
    "interval_second": 5,
    "hr_value_serial": 0,
    "hr_value": [
        85,
        86,
        90,
        79,
        88,
        92
    ]
}
```
