### Get Firmware Display Version

Function table: `supportGetFirmwareDisplayVersion`

**Flutter example:**

```dart
libManager.send(evt: CmdEvtType.getFirmwareDisplayVersion, json: jsonEncode({}));
```

**JSON fields in the response:**

| Field | Type | Description |
| ------ | -------- | -------- |
| err_code | int | `0`: success; other: failure |
| display_version | string | Firmware UI display version, e.g. `"1_00_09"` |

`Example:`

```json
{
  "err_code": 0,
  "display_version": "1_00_09"
}
```

**Notes:**

- Check `libManager.funTable.supportGetFirmwareDisplayVersion` before sending.
