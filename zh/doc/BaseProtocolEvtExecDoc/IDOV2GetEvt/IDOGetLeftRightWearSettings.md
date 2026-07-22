### 获取佩戴左右手设置

功能表: getLeftRightHandWearSettings

**Flutter example:**

```dart
/// 获取佩戴左右手设置
getLeftRightWearSettings(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_app_get_left_right_wear_settings),

/// 获取佩戴左右手设置
libManager.send(evt: CmdEvtType.getLeftRightWearSettings, json: jsonEncode(json));
```


**JSON fields received by App**:

| Field name | Field type | Field description |
| ------ | -------- | ---------------------------- |
| hand_type | int | 佩戴手表的手：0x00 左手，0x01 右手 |

`Example:`

```c
{
"hand_type":0,
}
```