### 设置语音助手开关


功能表：getSupportSetVoiceAssistantStatus

**Flutter示例：**

```dart
/// 设置手机语音助手开关
setVoiceAssistantOnOff(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_voice_assistant_on_off);

/// 设置手机语音助手开关
libManager.send(evt: CmdEvtType.setVoiceAssistantOnOff, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                 |
| ------ | -------- | ------------------------ |
| on_off | int      | 开关<br />0:关<br />1:开 |

`示例：`

```c
{
  "on_off" : 1
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明             |
| -------- | -------- | -------------------- |
| err_code | int      | 0是成功，非0是错误码 |


`示例：`

```c
{
  "err_code":0
}
```

