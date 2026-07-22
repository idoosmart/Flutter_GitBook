### V3 Emotional Health Reminder

Function table: supportEmotionHealth

**Flutter example:**

```dart
/// v3 Emotional Health Switch Setting
setEmotionHealthReminder(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.func_emotion_health),

/// v3 Emotional Health Switch Setting
libManager.send(evt: CmdEvtType.setEmotionHealthReminder, json: jsonEncode(json));
```

**JSON fields sent by App**:

| Field name | Field type | Field description |
| -------------- | -------- | ------------------------------------------------------------ |
| version | int | Protocol library version number |
| operate | int | Operation type 0: Invalid 1: Setting 2: Query |
| notify_type | int | Notification type: 0: Invalid 1: Allow notification; 2: Silent notification; 3: Turn off notification |
| emotional_health_switch | int | Emotional health master switch 1: On 0: Off |
| pressure_remind | Dictionary | Pressure high reminder configuration</br>pressure_switch</br>start_hour</br> start_minute</br>end_hour</br>end_minute</br>repetitions</br>reminder_interval |
| unpleasant_remind | Dictionary | Unpleasant reminder configuration</br>unpleasant_switch</br>unhappy_reminder_num |

| Field name | Field type | Field description |
| -------------- | -------- | --------------------------------------------------------- |
| pressure_switch | int | Pressure high reminder switch 1: On 0: Off |
| start_hour | int | Reminder start time (hours) |
| start_minute | int | reminder start time (minutes) |
| end_hour | int | reminder end time (hours) |
| end_minute | int | reminder end time (minutes) |
| repetitions | int | repetition cycle bit0 master switch 0 off 1 on, bit1~bit7 are Monday to Sunday, 1 repeat, 0 no repeat |
| reminder_interval | int | reminder interval, unit (minutes) |

| field name | field type | field description |
| -------------- | -------- | --------------------------------------------------------- |
| unpleasant_switch | int | unhappy reminder switch 1: on 0: off |
| unhappy_reminder_num | int | unhappy reminder threshold, 0 invalid |

`Example:`

```c
{
"operate": 1,
"notify_type": 1,
"emotional_health_switch": 1,
"pressure_remind": {
"pressure_switch":1,
"start_hour": 6,
"start_minute": 0,
"end_hour": 23,
"end_minute": 0,
"repetitions": 255,
"reminder_interval": 15
},
"unpleasant_remind": {
"unpleasant_switch":1,
"unhappy_reminder_num": 0,
}
}
```

**JSON fields received by App**:

| Field name | Field type | Field description |
| -------- | -------- | ------------------------- |
| version | int | Protocol library version number |
| error_code | int | Error code 0 success, non-0 is an error code |
| operate | int | Operation type 0: invalid 1: set 2: Query |
| emotional_health_switch | int | Emotional health switch 1: On 0: Off |
| notify_type | int | Notification type: 0: Invalid 1: Allow notification; 2: Silent notification; 3: Turn off notification |
| pressure_remind | Dictionary | Pressure high reminder configuration</br>pressure_switch</br>start_hour</br> start_minute</br>end_hour</br>end_minute</br>repetitions</br>reminder_interval |
| unpleasant_remind | Dictionary | Unpleasant reminder configuration</br>unpleasant_switch</br>unhappy_reminder_num |

| Field name | Field type | Field description |
| -------------- | -------- | --------------------------------------------------------- |
| pressure_switch | int | Pressure high reminder switch 1: On 0: Off |
| start_hour | int | Reminder start time (hour) |
| start_minute | int | Reminder start time (minute) |
| end_hour | int | Reminder end time (hour) |
| end_minute | int | Reminder end time (minute) |
| repetitions | int | Repetition cycle bit0 master switch 0 off 1 on, bit1~bit7 are Monday to Sunday, 1 repeat, 0 no repeat |
| reminder_interval | int | Reminder interval, unit (minute) |

| Field name | Field type | Field description |
| -------------- | -------- | --------------------------------------------------------- |
| unpleasant_switch | int | Unpleasant reminder switch 1: on 0: off  |
| unhappy_reminder_num | int | Unpleasant reminder threshold, 0 invalid |

`Example:`

```c
{
"operate": 1, 
"error_code":0, 
"notify_type": 1, 
"emotional_health_switch": 1, 
"pressure_remind": { 
    "pressure_switch":1, 
    "start_hour": 6, 
    "start_minute": 0, 
    "end_hour": 23, 
    "end_minute": 0, 
    "repetitions": 255, 
    "reminder_interval": 15 
}, 
"unpleasant_remind": { 
    "unpleasant_switch":1, 
    "unhappy_reminder_num": 6, 
}
}
```