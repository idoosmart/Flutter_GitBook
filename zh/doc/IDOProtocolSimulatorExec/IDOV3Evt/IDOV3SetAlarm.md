### V3APP设置ble的闹钟


功能表:syncV3SyncAlarm

**Flutter示例：**

```dart
/// v3app设置ble的闹钟事件号
setAlarmV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_alarm),

/// v3app设置ble的闹钟
libManager.send(evt: CmdEvtType.setAlarmV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名  | 字段类型 | 字段说明                                                     |
| ------- | -------- | ------------------------------------------------------------ |
| num     | int      | 闹钟详情个数                                                 |
| version | int      | 协议版本号，默认0                                            |
| item    | 集合     | 闹钟详情<br />`alarm_id`&`status`&`type`&`hour`&`minute`&`repeat`<br />&`tsnooze_duration`&`delay_min`&`name`&`shock_on_off`&`repeat_times`的集合 |

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| alarm_id     | int      | 闹钟id，从1开始，1~最大支持闹钟个数                          |
| status       | int      | 0 ：不显示(删除) <br />1 ：显示                              |
| type         | int      | 闹钟类型<br />00：起床<br />01：睡觉<br />02：锻炼<br />03：吃药<br />04：约会<br />05：聚会<br />06：会议<br />07：其他 |
| hour         | int      | 闹钟时间 时                                                  |
| minute       | int      | 闹钟时间 分                                                  |
| repeat       | int      | 重复<br />bit 0是总开关位,0关闭 1打开<br />bit1-bit7 周一到周日， 0不重复 1重复 |
| delay_min    | int      | 延时分钟<br />单位分钟                                       |
| name         | char []  | 闹钟名称，最大值23个字节                                     |
| shock_on_off | int      | 震动开关<br /> 0关闭 ，1开启                                 |
| repeat_times | int      | 重复闹铃次数 <br />重复闹几次,延时开关,设置成0就是关，设置成数字就是重复几次 |

`示例：`

```c
{
  "item" :
  [
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    },
    {
      "alarm_id" : 0,
      "delay_min" : 0,
      "hour" : 0,
      "minute" : 0,
      "name" : "",
      "repeat" : 0,
      "repeat_times" : 0,
      "shock_on_off" : 0,
      "status" : 0,
      "type" : 0
    }
  ],
  "num" : 10,
  "version" : 0
}
```
**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明         |
| ------ | -------- | ---------------- |
| status | int      | 0：成功，1：失败 |

`示例：`

```c
{
  "status" : 0
}
```

