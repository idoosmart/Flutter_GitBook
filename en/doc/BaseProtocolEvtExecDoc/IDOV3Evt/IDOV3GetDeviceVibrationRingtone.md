### Query device vibration and ringtone (V3 15.106)

Function table: `supportDeviceVibrationRingtone`

```dart
libManager.send(
  evt: CmdEvtType.deviceVibrationRingtone,
  json: jsonEncode({'operate': 1}),
);
```

Event ID: `358` (shared with set). See `IDOV3SetDeviceVibrationRingtone.md` for operate=2.
