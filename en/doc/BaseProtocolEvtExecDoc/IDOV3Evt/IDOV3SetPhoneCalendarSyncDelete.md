### Sync phone calendar deletions

Function table: `supportPhoneCalendarReminder`

**Flutter example:**

```dart
libManager.send(
  evt: CmdEvtType.phoneCalendarReminder,
  json: jsonEncode({
    'operate': 5,
    'item_count': 1,
    'items': [
      {
        'event_id': 'evt_001',
        'calendar_id': 'cal_work',
        'start_time': 1719000000,
      },
    ],
  }),
);
```

**Request JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| operate | int | `5` sync deletions |
| item_count | int | Optional; defaults to `items` length |
| items | array | Same item fields as [IDOV3GetPhoneCalendarDeleteList](./IDOV3GetPhoneCalendarDeleteList.md) response |

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

- Typical flow: device pending-delete notification → get delete list → delete on phone → this API.
- Delete list query: [IDOV3GetPhoneCalendarDeleteList](./IDOV3GetPhoneCalendarDeleteList.md).
