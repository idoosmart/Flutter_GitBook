### Query phone calendar sync switch

Function table: `supportPhoneCalendarReminder`

**Flutter example:**

```dart
libManager.send(
  evt: CmdEvtType.phoneCalendarReminder,
  json: jsonEncode({'operate': 2}),
);
```

**Request JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| operate | int | `2` query sync switch |

**Response JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| err_code | int | `0` success |
| sync_on_off | int | `1` sync on; `0` sync off |

`Example:`

```json
{
  "err_code": 0,
  "sync_on_off": 1
}
```

**Notes:**

- Set sync and permission: [IDOV3SetPhoneCalendarSync](./IDOV3SetPhoneCalendarSync.md).
