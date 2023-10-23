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

| 代码 | 天气类型 |
| ---- | -------- |
| 0x00 | 其他     |
| 0x01 | 晴       |
| 0x02 | 多云     |
| 0x03 | 阴       |
| 0x04 | 雨       |
| 0x05 | 暴雨     |
| 0x06 | 雷阵雨   |
| 0x07 | 雪       |
| 0x08 | 雨夹雪   |
| 0x09 | 台风     |
| 0x0A | 沙尘暴   |
| 0x0B | 夜间晴   |
| 0x0C | 夜间多云 |
| 0x0D | 热       |
| 0x0E | 冷       |
| 0x0F | 清风     |
| 0x10 | 大风     |
| 0x11 | 雾霾     |
| 0x12 | 阵雨     |
| 0x13 | 多云转晴 |
| 0x30 | 雷       |
| 0x31 | 冰雹     |
| 0x32 | 扬沙     |
| 0x33 | 龙卷风   |

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

