### 设置呼吸率开关


功能表：setRespirationRate

**Flutter示例：**

```dart
/// 设置呼吸率开关事件号
setRRespiRateTurn(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_respi_rate_on_off),

/// 设置呼吸率开关
libManager.send(evt: CmdEvtType.setRRespiRateTurn, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                  |
| ------ | -------- | ------------------------- |
| on_off | int      | 0：关闭 <br />1：开 |

`示例：`

```c
{
  "on_off":1
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
