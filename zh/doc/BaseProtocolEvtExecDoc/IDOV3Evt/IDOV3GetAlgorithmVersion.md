### V3APP获取固件算法版本号信息


功能表:getSupportGetV3DeviceAlgorithmVersion

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
| item    | 集合     | 闹钟详情<br />`alarm_id`&`status`&`type`&`hour`&`minute`&`repeat`<br />&`delay_min`&`name`&`shock_on_off`&`repeat_times`的集合 |

| 字段名           | 字段类型  | 字段说明                                                     |
| ---------------- | --------- | ------------------------------------------------------------ |
| alarm_id         | int       | 闹钟id，从1开始，1~最大支持闹钟个数                          |
| status           | int       | 0 ：不显示(删除) <br />1 ：显示<br />-1：无效                |
| type             | int       | 闹钟类型<br />00：起床<br />01：睡觉<br />02：锻炼<br />03：吃药<br />04：约会<br />05：聚会<br />06：会议<br />07：其他 |
| hour             | int       | 闹钟时间 时                                                  |
| minute           | int       | 闹钟时间 分                                                  |
| repeat           | int       | 重复<br />bit 0是总开关位,0关闭 1打开<br />bit1-bit7 周一到周日， 0不重复 1重复 |
| tsnooze_duration | int       | 预留                                                         |
| delay_min        | int       | 延时分钟                                                     |
| name             | char [24] | 闹钟名称，最大值24个字节                                     |
| shock_on_off     | int       | 震动开关<br />0关闭 <br />1开启                              |
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
