### 设置身体电量开关


功能表：syncV3BodyPower

**Flutter示例：**

```dart
/// 设置身体电量开关事件号
setBodyPowerTurn(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_body_power_on_off),

/// 设置身体电量开关
libManager.send(evt: CmdEvtType.setBodyPowerTurn, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                  |
| ------ | -------- | ------------------------- |
| on_off | int      | 85：关闭 <br />170：开 |

`示例：`

```c
{
  "on_off":170
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

