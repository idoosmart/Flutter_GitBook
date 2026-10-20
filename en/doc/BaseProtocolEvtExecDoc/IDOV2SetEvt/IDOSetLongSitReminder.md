### Set Sedentary Reminder

> Deprecated. Use walk reminder: [`Set Walk Reminder`](IDOSetWalkReminder.md) / [`Get Walk Reminder`](../IDOV2GetEvt/IDOGetWalkReminder.md).

Menu: setSedentariness (deprecated; use `setWalkReminder`)

**Flutter Example:**

```dart
/// Set Long Sit Event
setLongSit(
  evtBase: _VBusEvtBase.base_app_set, 
  evtType: _VBusEvtType.app_set_long_sit),

/// Set Long Sit
libManager.send(evt: CmdEvtType.setLongSit, json: jsonEncode(json));
```



**JSON Fields Sent by the App**:

| Field Name    | Field Type | Field Description                              |
| ------------- | ---------- | --------------------------------------------- |
| start_hour    | int        | Start Time of Sedentary Reminder (hour)        |
| start_minute  | int        | Start Time of Sedentary Reminder (minute)      |
| end_hour      | int        | End Time of Sedentary Reminder (hour)          |
| end_minute    | int        | End Time of Sedentary Reminder (minute)        |
| interval      | int        | Interval (in minutes) <br />Value should be greater than 15 minutes |
| repetitions   | int        | Repetitions and Switch<br />bit0: 0 means off, 1 means on <br />bit1-7: 0 means no repetition, 1 means repetition |

`Example:`

```json
{
  "start_hour": 15,
  "start_minute": 40,
  "end_hour": 23,
  "end_minute": 26,
  "interval": 15,
  "repetitions": 254
}
```



**JSON Field Received by the App**:

| Field Name   | Field Type | Field Description                     |
| ------------ | ---------- | ------------------------------------ |
| status_code  | int        | 0: Success, non-zero: Error code      |

`Example:`

```json
{
  "status_code": 0
}
```
