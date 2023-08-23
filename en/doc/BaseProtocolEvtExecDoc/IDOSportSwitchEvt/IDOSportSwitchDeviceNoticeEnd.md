#### App Notifies the Device About the Data Exchange Completion


**JSON Field Received by App**:

| Field Name     | Field Type | Field Description                                     |
| -------------- | ---------- | ---------------------------------------------------- |
| day            | int        | Start time: day                                      |
| hour           | int        | Start time: hour                                     |
| minute         | int        | Start time: minute                                   |
| second         | int        | Start time: second                                   |
| duration       | int        | Duration in seconds                                  |
| calories       | int        | Calories in kilocalories                             |
| distance       | int        | Distance in 0.01 km                                  |
| sport_type     | int        | Type of sport                                         |
| avg_hr_value   | int        | Average heart rate value                              |
| max_hr_value   | int        | Maximum heart rate value                              |
| burn_fat_mins  | int        | Duration of fat burning in minutes                    |
| aerobic_mins   | int        | Duration of aerobic exercise in minutes               |
| limit_mins     | int        | Duration of high-intensity exercise in minutes        |
| is_save        | int        | 0: Do not save, 1: Save                               |

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
    "avg_hr_value": 80,
    "max_hr_value": 90,
    "burn_fat_mins": 0,
    "aerobic_mins": 0,
    "limit_mins": 0,
    "is_save": 0
}
```

**JSON Field Sent by App**:

| Field Name | Field Type | Field Description                                |
| ---------- | ---------- | ------------------------------------------------ |
| err_code   | int        | err_code<br />0: Success<br />1: Failed: Not in exercise mode     |
| duration   | int        | Duration in seconds                             |
| calories   | int        | Calories in kilocalories                        |
| distance   | int        | Distance in 0.01 km                             |

`Example:`

```json
{
    "err_code": 0,
    "duration": 10,
    "calories": 50,
    "distance": 50
}
```
