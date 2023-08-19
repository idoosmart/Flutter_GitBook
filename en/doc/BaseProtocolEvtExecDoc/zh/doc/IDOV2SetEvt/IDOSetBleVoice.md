### 设置手机音量下发给设备


功能表：exTableMain10SetPhoneVoice(SDK待补充)

**Flutter示例：**

```dart
/// 手机音量下发给设备事件号
setBleVoice(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_ble_voice),

/// 手机音量下发给设备
libManager.send(evt: CmdEvtType.setBleVoice, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名      | 字段类型 | 字段说明   |
| ----------- | -------- | ---------- |
| total_voice | int      | 总音量     |
| now_voice   | int      | 当前的音量 |

`示例：`

```c
{
  "total_voice" : 100,
  "now_voice" : 85
}
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明             |
| ------ | -------- | -------------------- |
| state  | int      | 0是失败<br />1是成功 |


`示例：`
```c
{
  "state" : 1
}
```
