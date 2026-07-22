### Get left and right hand settings

Function table: getLeftRightHandWearSettings

**Flutter example:**

```dart
/// Get left and right hand settings
getLeftRightWearSettings(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_app_get_left_right_wear_settings),

/// Get left and right hand settings
libManager.send(evt: CmdEvtType.getLeftRightWearSettings, json: jsonEncode(json));
```

**JSON fields received by App**:

| Field name | Field type | Field description |
| ------ | -------- | ---------------------------- |
| hand_type | int | The hand wearing the watch: 0x00 left hand, 0x01 right hand |

`Example:`

```c
{
"hand_type":0,
}
```