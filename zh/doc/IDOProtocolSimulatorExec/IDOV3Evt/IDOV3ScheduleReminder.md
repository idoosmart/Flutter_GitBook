### V3日程提醒


功能表:setScheduleReminder 【getSupportSetRepeatWeekTypeOnScheduleReminderV3，getSupportSetRepeatTypeOnScheduleReminderV3】

**Flutter示例：**

```dart
/// v3 设置日程提醒事件号
setSchedulerReminderV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_scheduler_reminder),

/// v3 设置日程提醒
libManager.send(evt: CmdEvtType.setSchedulerReminderV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| version       | int      | 协议库版本号                                                 |
| operate       | int      | 操作类型<br />0：无效 <br />1：增 <br />2：删 <br />3：查<br />4：改 |
| num           | int      | 提醒事件详情个数,items的个数,设置起作用,其他时候是0, 每次发送1个 |
| items         | 集合     | 提醒事件详情 <br />最大设置1个数据                           |

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| id            | int      | 提醒事件id<br />每次app下发自增1，从0开始                    |
| year          | int      | 年                                                           |
| mon           | int      | 月                                                           |
| day           | int      | 日                                                           |
| hour          | int      | 时                                                           |
| min           | int      | 分                                                           |
| sec           | int      | 秒                                                           |
| repeat_type   | int      | 重复的时间 <br />开启`getSupportSetRepeatWeekTypeOnScheduleReminderV3`后重复提醒类型设置星期重复 bit1-bit7 周一到周日 bit 0是总开关位（开关）<br />开启`getSupportSetRepeatTypeOnScheduleReminderV3`后重复提醒类型设置(0:无效 1:仅一次 2:每天 3:每周 4:每月 5:每年） |
| remind_on_off | int      | 当天提醒开关<br /> 0是关， 1是开                             |
| state         | int      | 状态码 <br />0：无效, 1：删除状态, 2：启用状态               |
| title         | char []  | 标题内容 最大值74个字节                                      |
| note          | char []  | 提醒内容 最大值149个字节                                     |

`示例：`

```c
{
    "version":0,
    "operate":1,
    "num":1,
    "items":[
        {
            "id":0,
            "year":2022,
            "mon":12,
            "day":26,
            "hour":15,
            "min":51,
            "sec":20,
            "repeat_type":255,
            "remind_on_off":1,
            "state":2,
            "title":"提醒事项1",
            "note":"记得完成工作"
        }
    ]
}
```

**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| version       | int      | 协议库版本号                                                 |
| err_code      | int      | 错误码 0成功，非0是错误码                                    |
| num           | Int      | 固件中目前有多少提醒数据                                     |
| operate       | int      | 操作类型<br />0：无效 <br />1：增 <br />2：删 <br />3：查<br />4：改 |
| items         | 集合     | 提醒事件详情                                                 |

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| id            | int      | 提醒事件id<br />每次app下发自增1，从0开始                    |
| year          | int      | 年                                                           |
| mon           | int      | 月                                                           |
| day           | int      | 日                                                           |
| hour          | int      | 时                                                           |
| min           | int      | 分                                                           |
| sec           | int      | 秒                                                           |
| repeat_type   | int      | 重复的时间 <br />开启`getSupportSetRepeatWeekTypeOnScheduleReminderV3`后重复提醒类型设置星期重复 bit1-bit7 周一到周日 bit 0是总开关位（开关）<br />开启`getSupportSetRepeatTypeOnScheduleReminderV3`后重复提醒类型设置(0:无效 1:仅一次 2:每天 3:每周 4:每月 5:每年） |
| remind_on_off | int      | 当天提醒开关<br /> 0是关， 1是开                             |
| state         | int      | 状态码 <br />0：无效, 1：删除状态, 2：启用状态               |
| title         | char []  | 标题内容 最大值74个字节                                      |
| note          | char []  | 提醒内容 最大值149个字节                                     |


`示例：`

```c
{
    "version":0,
    "err_code":0,
    "num":0,
    "operate":1,
    "items":null
}
```

