#### App Sends Command to Start Exercise Data Exchange


**JSON Field Sent by App**:

| Field Name             | Field Type | Field Description                                                                     |
| ---------------------- | ---------- | ------------------------------------------------------------------------------------ |
| day                    | int        | Start time: day                                                                       |
| hour                   | int        | Start time: hour                                                                      |
| minute                 | int        | Start time: minute                                                                    |
| second                 | int        | Start time: second                                                                    |
| sport_type             | int        | Type of exercise                                                                      |
| target_type            | int        | Exercise goal<br />0: No goal<br />1: Repetitions (unit: times)<br />2: Distance (unit: meters)<br />3: Calories (unit: kcal)<br />4: Duration (unit: minutes)<br />5: Steps (unit: steps) |
| target_value           | int        | Goal value                                                                             |
| force_start            | int        | Force start<br />1: Force start enabled<br />0: Force start disabled (user only)       |
| vo2max                 | int        | Maximal oxygen consumption<br />Unit: ml/kg/min (app stores the received data)        |
| recover_time           | int        | Recovery time<br />Unit: hours (app will decrement by one every hour)                   |
| avg_week_activity_time | int        | Average weekly activity time of last month<br />Unit: minutes                           |

`Example:`

```json
{
    "day": 26,
    "hour": 10,
    "minute": 43,
    "second": 10,
    "sport_type": 10,
    "target_type": 1,
    "target_value": 1,
    "force_start": 0,
    "vo2max": 10,
    "recover_time": 1,
    "avg_week_activity_time": 1
}
```

**JSON Field Received by App**:

| Field Name | Field Type | Field Description                                                                 |
| ---------- | ---------- | -------------------------------------------------------------------------------- |
| ret_code   | int        | ret_code<br/>0: Success<br/>1: Failed to enter exercise mode on the device<br/>2: Device low battery<br/>3: Charging<br/>4: Restricted by Alexa  |

`Example:`

```json
{
    "ret_code": 0
}
```

