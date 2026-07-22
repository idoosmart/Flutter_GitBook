### Get phone calendar delete list

Function table: `supportPhoneCalendarReminder`

**Flutter example:**

```dart
libManager.send(
  evt: CmdEvtType.phoneCalendarReminder,
  json: jsonEncode({'operate': 4}),
);
```

**Request JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| operate | int | `4` query delete list |

**Response JSON fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| err_code | int | `0` success |
| item_count | int | Item count |
| items | array | Delete list; see item fields below |

**Item fields:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| event_id | string | Event ID |
| calendar_id | string | Calendar ID |
| start_time | int | Start UTC seconds; `0` deletes all under event+calendar |

`Example:`

```json
{
  "err_code": 0,
  "item_count": 1,
  "items": [
    {
      "event_id": "evt_001",
      "calendar_id": "cal_work",
      "start_time": 1719000000
    }
  ]
}
```

**Notes:**

- Call after the device pending-delete notification; after deleting on the phone calendar, use [IDOV3SetPhoneCalendarSyncDelete](./IDOV3SetPhoneCalendarSyncDelete.md) to sync the device.
- Local calendar deletes may call delete-sync directly without querying this list first.
