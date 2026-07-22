### Get device status (GET:0x02/0x49)

Function table: `supportGetDeviceStatus`, `supportGetDeviceSportStatus`

**Flutter example:**

```dart
libManager.send(
  evt: CmdEvtType.getDeviceStatusInfo,
  json: jsonEncode({'get_type': 1}),
);
```

**Response JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| get_type | int | Query mask echoed back |
| has_sport_start_type | bool | Whether sport status is present |
| sport_start_type | int | `0` idle; `1` app-started sport; `2` watch-started; `3` auto-detected sport |

Event ID: `361`.
