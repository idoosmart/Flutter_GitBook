### Take Medicine Reminder

Function table: `supportTakeMedicineReminder`

**Flutter example (query):**

```dart
libManager.send(
  evt: CmdEvtType.takeMedicineRemind,
  json: jsonEncode({'operate': 2}),
);
```

**operate values:**

| operate | Meaning |
| ---: | :--- |
| 1 | Set one reminder item |
| 2 | Query all reminder items |
| 3 | Delete by `index` |
| 4 | Set display master switch only |

**Request JSON (by operate):**

| Field | Type | operate | Description |
| ----- | ---- | ------- | ----------- |
| operate | int | all | See table above |
| medicine_show_on_off | int | 1, 4 | `1` on / `0` off / `255` invalid; required for operate=4 |
| take_medicine_info_count | int | 1 | `1` with detail / `0` without |
| take_medicine_info_item | object | 1 | Single reminder detail |
| index | int | 3 | Item index to delete (from `1`) |

operate=2 query needs **only** `operate`.

**Response JSON:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| operate | int | Echo of request operate |
| error_code | int | `0` success; `1` failure |

operate=1/3/4 responses include **only** the two fields above.

operate=2 query adds `medicine_show_on_off` (`1` on / `0` off / `255` invalid), `max_support_items_num`, and `take_medicine_info_items` (array, `[]` when empty); `time_items[]` includes `reminder_status`.

**Example (query response):**

```json
{
  "operate": 2,
  "error_code": 0,
  "medicine_show_on_off": 0,
  "max_support_items_num": 6,
  "take_medicine_info_items": []
}
```

**Notes:**

- Use `1` / `0` / `255` for `medicine_show_on_off`, not `170` / `85`.
- Packet fields are merged internally; response has no `all_items_num` etc.
