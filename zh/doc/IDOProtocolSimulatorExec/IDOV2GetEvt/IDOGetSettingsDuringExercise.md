### 获取运动中设置提示音开关

**Flutter示例：**

```dart
/// 获取运动中设置提示音开关事件号
getSettingsDuringExercise(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.vbus_evt_app_get_settings_during_exercise),

/// 获取运动中设置提示音开关
libManager.send(evt: CmdEvtType.getSettingsDuringExercise);
```

**App下发的json字段**:
无参数

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| notification_switch | int | 提示音开关：<br />0xAA (170): 打开<br />0x55 (85): 关闭 |

`示例：`

```json
{
    "notification_switch": 170
}
```
