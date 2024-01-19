### 设置屏幕亮度


功能表：setScreenBrightness 【v2SupportSetBrightScreenTime，v2SupportAdjustNightTurnOnAfterSunset，v2SupportAddNightLevel，nightAutoBrightness】

**Flutter示例：**

```dart
/// 设置屏幕亮度事件号
setScreenBrightness(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_screen_brightness),

/// 设置屏幕亮度
libManager.send(evt: CmdEvtType.setScreenBrightness, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| level             | int      | 亮度等级<br />0-100                                          |
| opera             | int      | 0 自动同步配置<br />1 用户手动调节                           |
| mode              | int      | 0：指定等级<br />1：使用环境光传感器<br />2：level不起作用   |
| auto_adjust_night | int      | 夜间自动亮度调整 <br />0：无效,由固件定义<br />1：关闭<br />2：夜间自动调整亮度<br />3：夜间降亮度使用设置的时间<br />功能表`nightAutoBrightness`开启有效 |
| start_hour        | int      | 开始时间时<br />功能表`v2SupportSetBrightScreenTime`开启有效 |
| start_minute      | int      | 开始时间分<br />功能表`v2SupportSetBrightScreenTime`开启有效 |
| end_hour          | int      | 结束时间时<br />功能表`v2SupportSetBrightScreenTime`开启有效 |
| end_minute        | int      | 结束时间分<br />功能表`v2SupportSetBrightScreenTime`开启有效 |
| night_level       | int      | 夜间亮度<br />0-100<br />功能表`v2SupportAddNightLevel`开启有效 |
| show_interval     | int      | 显示间隔<br />0无效<br />单位:秒                             |

`示例：`

```c
{
  "level":20,
  "opera":0,
  "mode":0,
  "auto_adjust_night":3,
  "start_hour":18,
  "start_minute":0,
  "end_hour":23,
  "end_minute":0,
  "night_level":20,
  "show_interval":0
}
```

