### Set device vibration and ringtone (V3 15.106)

```dart
libManager.send(
  evt: CmdEvtType.deviceVibrationRingtone,
  json: jsonEncode({
    'operate': 2,
    'type': 3,
    'vibration_intensity': 2,
    'alarm_volume': 5,
  }),
);
```

Event ID: `358`. Response: `operate`, `ret_code`.
