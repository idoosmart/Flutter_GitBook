### 设置压力开关


功能表：setPressureData 【getPressureNotifyFlagMode，v2SendCalibrationThreshold(SDK待补充)】

**Flutter示例：**

```dart
/// 设置压力开关事件号
setStressSwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_pressure),

/// 设置压力开关
libManager.send(evt: CmdEvtType.setStressSwitch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| on_off           | int      | 总开关 <br />170开 85关闭                                 |
| start_hour       | int      | 开始时间 时                                                  |
| start_minute     | int      | 开始时间 分                                                  |
| end_hour         | int      | 结束时间 时                                                  |
| end_minute       | int      | 结束时间 分                                                  |
| remind_on_off    | int      | 压力提醒开关 <br />170开 85关<br />on_off为关则提醒不起作用 |
| repeat           | int      | bit0 无效,bit1-bit7 分别是星期1到星期7,同闹钟                |
| interval         | int      | 提醒间隔,单位分钟 默认60分钟                                 |
| high_threshold   | int      | 压力过高阈值                                                 |
| stress_threshold | int      | 压力校准阈值，默认是80 <br />需要固件开启功能表支持 v2_send_calibration_threshold |
| notify_flag      | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 <br />需要固件开启功能表支持 V3_pressure_add_notify_flag_and_mode |

`示例：`

```c
{
   "on_off":170,
   "start_hour":14,
   "start_minute":0,
   "end_hour":20,
   "end_minute":0,
   "remind_on_off":170,
   "repeat":127,
   "interval":60,
   "high_threshold":170,
   "stress_threshold":80,
   "notify_flag":1
}
```
