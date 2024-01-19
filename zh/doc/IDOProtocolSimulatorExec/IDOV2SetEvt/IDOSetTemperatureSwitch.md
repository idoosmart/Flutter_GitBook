### 设置夜间体温开关


功能表：setTemperatureSwitchSupport

**Flutter示例：**

```dart
/// 设置夜间体温开关事件号
setTemperatureSwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_temperature_switch),

/// 设置夜间体温开关
libManager.send(evt: CmdEvtType.setTemperatureSwitch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| mode         | int      | 模式 <br />1：开<br />0：关闭                                |
| start_hour   | int      | 开始时间 时                                                  |
| start_minute | int      | 开始时间 分                                                  |
| end_hour     | int      | 结束时间 时                                                  |
| end_minute   | int      | 结束时间 分                                                  |
| unit         | int      | 体温单位设置：<br /> 1：c（摄氏度）  <br /> 2：f（华摄氏度） |

`示例：`

```json
{
  "mode":1,
  "start_hour":19,
  "start_minute":0,
  "end_hour":23,
  "end_minute":0,
  "unit":1
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`
```c
{
  "is_success":0
}
```

