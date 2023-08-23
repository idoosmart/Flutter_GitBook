#### APP Sends Data Exchange Completion for Exercise


**JSON Field Sent by App**:

| Field Name   | Field Type | Field Description           |
| ------------ | ---------- | --------------------------- |
| day          | int        | Start time: day             |
| hour         | int        | Start time: hour            |
| minute       | int        | Start time: minute          |
| second       | int        | Start time: second          |
| duration     | int        | Duration in seconds         |
| calories     | int        | Calories in kilocalories    |
| distance     | int        | Distance in 0.01 km         |
| sport_type   | int        | Sport type                  |
| is_save      | int        | 0: Not saved, 1: Saved      |

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 50,
    "second": 50,
    "duration": 10,
    "calories": 10,
    "distance": 10,
    "sport_type": 1,
    "is_save": 0
}
```

**JSON Field Received by App**:

| Field Name      | Field Type | Field Description                                                                       |
| --------------- | ---------- | -------------------------------------------------------------------------------------- |
| err_code        | int        | err_code<br />0: Success<br />1: Failed: Device not in exercise mode<br />2: Device stopped exercise (exercise already ended) |
| step            | int        | Step count / Repetitions                                                                |
| calories        | int        | Calories in kilocalories                                                               |
| distance        | int        | Distance in 0.01 km                                                                    |
| avg_hr_value    | int        | Average heart rate                                                                      |
| max_hr_value    | int        | Maximum heart rate                                                                      |
| burn_fat_mins   | int        | Duration of fat burning exercise in minutes                                             |
| aerobic_mins    | int        | Duration of aerobic exercise in minutes                                                 |
| limit_mins      | int        | Duration of limit exercise in minutes                                                   |

`Example:`

```json
{
    "err_code": 0,
    "step": 200,
    "calories": 20,
    "distance": 50,
    "avg_hr_value": 80,
    "max_hr_value": 90,
    "burn_fat_mins": 0,
    "aerobic_mins": 0,
    "limit_mins": 0
}
```
