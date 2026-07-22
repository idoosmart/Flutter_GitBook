### Set phone calendar sync switch and permission

Function table: `supportPhoneCalendarReminder`

**Flutter example:**

```dart
libManager.send(
  evt: CmdEvtType.phoneCalendarReminder,
  json: jsonEncode({
    'operate': 3,
    'sync_on_off': 1,
    'calendar_permission_status': 1,
  }),
);
```

**Request JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| operate | int | `3` set sync switch and permission |
| sync_on_off | int | `1` sync on; `0` sync off |
| calendar_permission_status | int | `1` permission granted; `0` denied |

**Response JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| err_code | int | `0` success |

`Example:`

```json
{
  "err_code": 0
}
```

**Notes:**

- Query sync switch: [IDOV3GetPhoneCalendarSyncSwitch](./IDOV3GetPhoneCalendarSyncSwitch.md).
- `calendar_permission_status` should reflect current system calendar read permission.
