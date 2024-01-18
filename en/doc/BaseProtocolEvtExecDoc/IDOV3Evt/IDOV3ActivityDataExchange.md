### V3 Sports Data Exchange

Function: exchangeAppV3Ing

**Flutter Example:**

```dart
/// app initiates the V3 data exchange process event number
exchangeAppV3Ing(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_activity_data_exchange),

/// app initiates the V3 data exchange process
libManager.send(evt: CmdEvtType.exchangeAppV3Ing, json: jsonEncode(json));
```

**JSON Fields Sent by the App**:

| Field Name      | Field Type | Field Description                                              |
| --------------- | ---------- | ------------------------------------------------------------- |
| version         | int        | Protocol version number. Default: 0<br />16: biggerfive custom project (requires firmware to enable V3_support_v3_exchange_data_reply_add_real_time_speed_pace)<br />32: Added running plan data (requires firmware to enable v3_support_sports_plan) |
| type            | int        | Sports type                                                    |
| signal_flag     | int        | 0: Weak signal<br />1: Strong signal                           |
| distance        | int        | Distance recorded by the app. When the app signal strength is strong, BLE calculates the distance using the app's data. When the app signal is weak, BLE does not use the app's data, and the app displays the data from the bracelet. |
| real_time_speed | int        | Real-time speed calculated and displayed by the app, in km/h, multiplied by 100 |
| duration        | int        | Duration                                                      |
| calories        | int        | Calories burned                                               |

**Example:**

```json
{
  "version": 0,
  "type": 0,
  "signal_flag": 0,
  "distance": 0,
  "real_time_speed": 0,
  "duration": 0,
  "calories": 0
}
```

**JSON Fields Received by the App**:

| Field Name           | Field Type | Field Description                                              |
| -------------------- | ---------- | ------------------------------------------------------------- |
| version              | int        | Protocol version number<br />0: Basic version<br />16: biggerfive custom project (requires firmware to enable V3_support_v3_exchange_data_reply_add_real_time_speed_pace)<br />32: Added running plan data (requires firmware to enable v3_support_sports_plan) |
| type                 | int        | Sports type. Valid when act_type is 0                          |
| day                  | int        | Data date (day)                                               |
| hour                 | int        | Data time (hour)                                              |
| minute               | int        | Data time (minute)                                            |
| second               | int        | Data time (second)                                            |
| heart_rate           | int        | Heart rate data                                               |
| distance             | int        | Distance. The unit is determined by the unit settings         |
| real_time_speed      | int        | Real-time speed in km/h, multiplied by 100                     |
| km_speed             | int        | Real-time kilometer pace, in seconds per kilometer             |
| real_time_calories   | int        | Dynamic calorie count                                         |
| steps                | int        | Number of steps                                               |
| swim_posture         | int        | Main swimming posture                                         |
| status               | int        | Status<br />0: Invalid<br />1: Start<br />2: Manually paused<br />3: End<br />4: Auto paused |
| duration             | int        | Duration in seconds                                           |
| real_time_speed_pace | int        | Real-time pace in seconds<br />5-second moving average. The 5th second uses the data from 1st to 5th second, and the 6th second uses the data from 2nd to 6th second. No pace or speed is displayed for the 1st to 4th seconds.<br />Requires the firmware to enable V3_support_v3_exchange_data_reply_add_real_time_speed_pace. Returns 0 if the feature is not enabled |
| te                   | int        | Aerobic training effect level. No unit. Range: 0-50. Transmitted by scaling up by 10<br />Requires the firmware to enable V3_support_v3_exchange_data_reply_add_real_time_speed_pace. Returns 0 if the feature is not enabled |
| tean                 | int        | Anaerobic training effect level. No unit. Range: 0-50. Transmitted by scaling up by 10<br />Requires the firmware to enable V3_support_v3_exchange_data_reply_add_real_time_speed_pace. Returns 0 if the feature is not enabled |
| action_type          | int        | Action type<br />1: Fast walking<br />2: Jogging<br />3: Medium-speed running<br />4: Sprinting<br />5: End of exercise (also waiting for user to start free exercise)<br />6: Free exercise after the end of the workout (this field is effective when operate is 5)<br />Cumulative exercise time = training time within the session + time after the session ends<br />Requires the firmware to enable v3_support_sports_plan. Returns 0 if the feature is not enabled |
| count_hour           | int        | When action_type is 1-5, this field is the countdown time (note: time decreases)<br />When action_type is 6, this field is the time after the session ends (note: time increases)<br />Requires the firmware to enable v3_support_sports_plan. Returns 0 if the feature is not enabled |
| count_minute         | int        | When action_type is 1-5, this field is the countdown time (note: time decreases)<br />When action_type is 6, this field is the time after the session ends (note: time increases)<br />Requires the firmware to enable v3_support_sports_plan. Returns 0 if the feature is not enabled |
| count_second         | int        | When action_type is 1-5, this field is the countdown time (note: time decreases)<br />When action_type is 6, this field is the time after the session ends (note: time increases)<br />Requires the firmware to enable v3_support_sports_plan. Returns 0 if the feature is not enabled |

**Example:**

```json
{
  "version": 0,
  "type": 0,
  "day": 0,
  "hour": 0,
  "minute": 0,
  "second": 0,
  "heart_rate": 0,
  "distance": 0,
  "real_time_speed": 0,
  "km_speed": 0,
  "real_time_calories": 0,
  "steps": 0,
  "swim_posture": 0,
  "status": 0,
  "duration": 0,
  "real_time_speed_pace": 0,
  "te": 0,
  "tean": 0,
  "action_type": 0,
  "count_hour": 0,
  "count_minute": 0,
  "count_second": 0
}
```

