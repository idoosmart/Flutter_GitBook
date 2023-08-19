### V3设置运动城市名称


**Flutter示例：**

```dart
/// v3 设置运动城市名称事件号
setLongCityNameV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_long_city_name),

/// v3 设置运动城市名称
libManager.send(evt: CmdEvtType.setLongCityNameV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名  | 字段类型 | 字段说明                   |
| ------- | -------- | -------------------------- |
| version | int      | 协议库版本号               |
| name    | char []   | 城市名称<br />最大75个字节 |

`示例：`

```c
{
    "version":0,
    "name":"shenzhen"
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                  |
| -------- | -------- | ------------------------- |
| version  | int      | 协议库版本号              |
| err_code | int      | 错误码 0成功，非0是错误码 |

`示例：`

```c
{
    "version":0,
    "err_code":0
}
```

