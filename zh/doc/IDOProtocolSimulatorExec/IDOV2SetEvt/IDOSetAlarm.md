### 添加闹钟


功能表:

**Flutter示例：**

```dart
/// 设置闹钟事件号
setAddAlarm(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_add_alarm),

/// 设置闹钟
libManager.send(evt: CmdEvtType.setAddAlarm, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名      | 字段类型 | 字段说明                                                     |
| ----------- | -------- | ------------------------------------------------------------ |
| alarm_num   | int      | 闹钟个数                                                     |
| alarm_items | 集合     | 闹钟详情 `alarm_id` & `alarm_type` & `alarm_hour` & `alarm_minute` & `alarm_status` & `tsnooze_duration` & `repeat`的集合 |

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| alarm_id         | int      | 闹钟id号,固定(1\~最多支持闹钟个数)                           |
| alarm_type       | int      | 类型：<br />0:起床<br />1:睡觉<br />2:锻炼<br />3:吃药<br />4:约会<br />5:聚会<br />6:会议<br />7:其他<br />8:吃饭<br />9:刷牙<br />10:休息<br />11:课程<br />12:洗澡<br />13:学习<br />14:玩耍时间 |
| alarm_hour       | int      | 闹钟时(24小时制)                                             |
| alarm_minute     | int      | 闹钟分(24小时制)                                             |
| alarm_status     | int      | 状态<br />1:显示<br />0:不显示                               |
| tsnooze_duration | int      | 贪睡时长<br />0\~60<br />0表示不贪睡<br />单位:分钟          |
| repeat           | int      | 重复及开关<br />bit0 总开关:0表示关,1表示开 <br />bit1-7 每个bit对应星期1~7 <br />1:重复提醒 0:不重复提醒 |

`示例：`

```c
{
  "alarm_num":10,
  "alarm_items":[
    {
      "alarm_id":1,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":1,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":2,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":3,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":4,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":85,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":5,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":6,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":7,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":8,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":9,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    },
    {
      "alarm_id":10,
      "alarm_type":0,
      "alarm_hour":9,
      "alarm_minute":0,
      "alarm_status":0,
      "tsnooze_duration":5,
      "repeat":285
    }
  ]
}
```
