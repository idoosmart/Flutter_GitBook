### Get Stress Value

Menu: setSetStressCalibration

**Flutter Example:**

```dart
/// Get stress value event number
getStressVal(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_stress_val),

/// Get stress value
libManager.send(evt: CmdEvtType.getStressVal, json: jsonEncode(json));
```

**JSON Fields Received by the App:**

| Field Name  | Field Type | Field Description |
| ----------- | ---------- | ---------------- |
| stress_val  | int        | Stress value      |
| threshold   | int        | Threshold         |

**Example:**

```c
{
    "stress_val":0,
    "threshold":0
}
```