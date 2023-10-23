### 设置天气城市名称


功能表：setWeatherCity 【v3SupportV3LongCityName】

**Flutter示例：**

```dart
/// 设置天气城市名称事件号
setWeatherCityName(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_weatcher_city_name),

/// 设置天气城市名称
libManager.send(evt: CmdEvtType.setWeatherCityName, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| version   | int      | 版本号0                                                      |
| city_name | char []  | 城市名称 <br />v3SupportV3LongCityName开启后后支持74个字节大小的城市名称<br />v3SupportV3LongCityName不开启功能表默认16个字节大小 |

`示例：`

```c
{
  "version":0,
  "city_name":"shenzhen"
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明             |
| -------- | -------- | -------------------- |
| version  | int      | 0是失败<br />1是成功 |
| err_code | int      | 0成功，非0是错误码   |

`示例：`
```c
{
  "version":0,
  "err_code":0
}
```
