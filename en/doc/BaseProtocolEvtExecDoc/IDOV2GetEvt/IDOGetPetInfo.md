### Get pet info

Function table: supportPetInfo

**Flutter Example:**

```dart
/// Event for get pet info
/// getPetInfo(
///   evtBase: _VBusEvtBase.base_app_get,
///   evtType: _VBusEvtType.app_get_pet_info),

libManager.send(evt: CmdEvtType.getPetInfo, json: jsonEncode({}));
```

**JSON fields received by App**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ---------------- |
| pet_type   | int        | Pet type: 0 invalid, 1 cat, 2 dog |
| weight     | int        | Weight x100, unit kg |
| gender     | int        | Gender: 0 male, 1 female |
| year       | int        | Birth year |
| month      | int        | Birth month |
| day        | int        | Birth day |

`Example:`

```json
{
  "pet_type": 1,
  "weight": 450,
  "gender": 0,
  "year": 2024,
  "month": 1,
  "day": 1
}
```

**Notes:**

- It is recommended to check `libManager.funTable.supportPetInfo` before sending.
