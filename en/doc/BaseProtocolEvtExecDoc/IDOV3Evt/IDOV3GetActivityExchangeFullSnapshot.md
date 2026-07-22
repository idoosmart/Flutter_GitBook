### V3 activity full snapshot during sport (15.103)

Function table: `supportV3ActivityExchangeFullSnapshot`

```dart
libManager.send(
  evt: CmdEvtType.getActivityExchangeFullSnapshot,
  json: jsonEncode({}),
);
```

Event ID: `5114`. Returns full sport snapshot JSON after disconnect; protocol handles packet reassembly internally.
