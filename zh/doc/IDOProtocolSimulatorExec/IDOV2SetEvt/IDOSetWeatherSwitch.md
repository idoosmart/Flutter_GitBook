### 设置天气开关

功能表：setSetV3Weather

**Flutter示例：**

```dart
/// 设置天气开关事件号
setWeatherSwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_weather_switch),

/// 设置天气开关
libManager.send(evt: CmdEvtType.setWeatherSwitch, json: jsonEncode(json));
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

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

