### Get App Sleep Mode

Function table: supportAppSleepMode

**Flutter example:**

```dart
/// Get app sleep mode event
/// getAppSleepMode(
///   evtBase: _VBusEvtBase.base_app_get,
///   evtType: _VBusEvtType.app_get_app_sleep_mode),

/// Get app sleep mode
libManager.send(evt: CmdEvtType.getAppSleepMode, json: jsonEncode({}));
```

**Response JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| sleep_mode_switch | int | Sleep mode switch<br />1: on<br />0: off<br />255: invalid |
| sleep_hour | int | Bedtime hour, 0~23 |
| sleep_minute | int | Bedtime minute, 0~59 |
| awake_hour | int | Wake hour, 0~23 |
| awake_minute | int | Wake minute, 0~59 |
| repeat | int | Repeat mask<br />bit0 invalid<br />bit1~bit7 Mon~Sun |
| wake_alarm_repeat_cnt | int | Wake alarm repeat count, 0~3 |
| wake_alarm_delay_time | int | Wake alarm delay in minutes, 1~15 |

`Example:`

```json
{
  "sleep_mode_switch": 1,
  "sleep_hour": 22,
  "sleep_minute": 0,
  "awake_hour": 7,
  "awake_minute": 0,
  "repeat": 62,
  "wake_alarm_repeat_cnt": 3,
  "wake_alarm_delay_time": 10
}
```

**Notes:**

- Check `libManager.funTable.supportAppSleepMode` before sending.
- When `sleep_mode_switch` is `255`, treat as invalid/unsupported.
- Protocol cmd/key: `02 4C`; event id `367`.
