### 获取左右手佩戴设置

**Flutter示例：**

```dart
/// 获取左右手佩戴设置事件号
getLeftRightWearSettings(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.vbus_evt_app_get_left_right_wear_settings),

/// 获取左右手佩戴设置
libManager.send(evt: CmdEvtType.getLeftRightWearSettings);
```

**App下发的json字段**:
无参数

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| hand_type | int | 佩戴方式：<br />0：左手<br />1：右手 |

`示例：`

```json
{
    "hand_type": 0
}
```
