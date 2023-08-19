### V3APP获取设备的闹钟


功能表:syncV3SyncAlarm

**Flutter示例：**

```dart
/// v3app获取ble的闹钟事件号
getAlarmV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_alarm),

/// v3app获取ble的闹钟
libManager.send(evt: CmdEvtType.getAlarmV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| flag   | int      | 获取闹钟标志<br />0:获取所有的闹钟<br />1:收到通知，获取手环修改的闹钟 |

**App收到的json字段**：

| 字段名  | 字段类型 | 字段说明                                                     |
| ------- | -------- | ------------------------------------------------------------ |
| num     | int      | 闹钟详情个数                                                 |
| version | int      | 协议版本号，默认0                                            |
| item    | 集合     | 闹钟详情<br />alarm_id&status&type&hour&minute&repeat<br />&tsnooze_duration&delay_min&name&shock_on_off&repeat_times的集合 |

| 字段名           | 字段类型  | 字段说明                                                     |
| ---------------- | --------- | ------------------------------------------------------------ |
| alarm_id         | int       | 闹钟id                                                       |
| status           | int       | 170 ：不显示(删除) ，85 ：显示                            |
| type             | int       | 闹钟类型<br />00：起床， 01 睡觉， 02 锻炼， 03 吃药， 04 约会， 05 聚会， 06 会议， 07 其他 |
| hour             | int       | 闹钟时间 时                                                  |
| minute           | int       | 闹钟时间 分                                                  |
| repeat           | int       | 重复<br />bit1-bit7 周一到周日， bit 0是总开关位（开关）     |
| tsnooze_duration | int       | 贪睡时长 单位分钟还是秒                                      |
| delay_min        | int       | 延时分钟                                                     |
| name             | char [24] | 闹钟名称，最大值24个字节                                     |
| shock_on_off     | int       | 震动开关<br /> 0关闭 ，1开启                                 |
| repeat_times     | int       | 重复闹铃次数 <br />重复闹几次,延时开关,设置成0就是关，设置成数字就是重复几次 |

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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
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
      "tsnooze_duration" : 0,
      "type" : 0
    }
  ],
  "num" : 10,
  "version" : 0
}
```
