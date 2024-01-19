### 获取屏幕亮度


功能表:getScreenBrightnessMain9

**Flutter示例：**

```dart
/// 获取屏幕亮度事件号
getScreenBrightness(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_screen_brightness),

/// 获取屏幕亮度
libManager.send(evt: CmdEvtType.getScreenBrightness, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| level             | int      | 亮度等级<br />(0-100)                                        |
| opera             | int      | 0 自动<br />1 手动 <br />如果是自动同步配置,请发送00,如果是用户调节请发送01 |
| mode              | int      | 0 指定等级<br />1 使用环境光传感器<br />2 level不起作用 |
| auto_adjust_night | int      | 夜间自动亮度调整 <br />0 无效,由固件定义<br />1 关闭<br />2 夜间自动调整亮度<br />3 夜间降亮度使用设置的时间 |
| start_hour        | int      | 开始时间 时                                                  |
| start_minute      | int      | 开始时间 分                                                  |
| end_hour          | int      | 结束时间 时                                                  |
| end_minute        | int      | 结束时间 分                                                  |
| night_level       | int      | 夜间亮度                                                     |
| show_interval     | int      | 显示间隔                                                     |

`示例：`

```c
{
  "auto_adjust_night" : 1,
  "end_hour" : 6,
  "end_minute" : 0,
  "level" : 60,
  "mode" : 0,
  "night_level" : 0,
  "opera" : 1,
  "show_interval" : 5,
  "start_hour" : 19,
  "start_minute" : 0
 }
```
