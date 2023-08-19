### 设置天气数据


功能表：getWeather

**Flutter示例：**

```dart
/// 设置天气数据事件号
setWeatherData(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_weatcher_data),

/// 设置天气数据
libManager.send(evt: CmdEvtType.setWeatherData, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                                 |
| ------------ | -------- | -------------------------------------------------------- |
| type         | int      | 天气类型                                                 |
| temp         | int      | 当前温度                                                 |
| max_temp     | int      | 当天最高温度                                             |
| min_temp     | int      | 当天最低温度                                             |
| humidity     | int      | 当前湿度                                                 |
| uv_intensity | int      | 当前紫外线强度                                           |
| aqi          | int      | 当前污染指数                                             |
| future       | 集合     | 未来三天的天气情况<br />type & min_temp & max_temp的集合 |

| 字段名   | 字段类型 | 字段说明     |
| -------- | -------- | ------------ |
| type     | int      | 未来天气类型 |
| min_temp | int      | 未来最高温度 |
| max_temp | int      | 未来最低温度 |

`示例：`

```c
{
  "type":1,
  "temp":10,
  "max_temp":18,
  "min_temp":7,
  "humidity":20,
  "uv_intensity":30,
  "aqi":60,
  "future":[
  {
      "type":2,
      "min_temp":10,
      "max_temp":18
  },
  {
      "type":2,
      "min_temp":9,
      "max_temp":16
  },
  {
      "type":1,
      "min_temp":8,
      "max_temp":19
  }
  ]
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

