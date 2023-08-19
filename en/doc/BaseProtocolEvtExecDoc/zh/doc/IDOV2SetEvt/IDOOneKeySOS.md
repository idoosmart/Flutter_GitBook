### 设置一键呼叫


功能表: onetouchCalling(SDK待补充)

**Flutter示例：**

```dart
/// 设置一键呼叫事件号
setOnekeySOS(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_onekey_sos),

/// 设置一键呼叫
libManager.send(evt: CmdEvtType.setOnekeySOS, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名     | 字段类型 | 字段说明                                                |
| ---------- | -------- | ------------------------------------------------------- |
| on_off     | int      | 开关<br />170 开 <br />85 关                         |
| phone_type | int      | 0：无效 <br />1：doro手机  <br />2：非doro手机 |

`示例：`

```c
{
  "on_off":85,
  "phone_type":0
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

