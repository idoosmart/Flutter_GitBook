### V3获取用户习惯信息


**Flutter示例：**

```dart
/// v3获取固件本地提示音文件信息
getHabitInfoV3(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_habit_information
),

/// v3获取固件本地提示音文件信息
libManager.send(evt: CmdEvtType.getHabitInfoV3, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| browse_count    | int      | 浏览打点详情个数                                             |
| implement_count | int      | 执行打点详情个数                                             |
| bro_items       | 集合     | 浏览打点详情<br />type & evt & year & month & day & hour & min & sec &count的集合 |
| imp_items       | 集合     | 执行打点详情<br />type & evt & start_year & start_month & start_day & start_hour & start_min & start_sec & end_year & end_month & end_day & end_hour & end_min & end_sec & completion_rate的集合 |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| type   | int      | 特性名称 <br />1：跑步课程  <br />2：跑步计划<br />3：设备睡眠<br />4：体重 |
| evt    | int      | 事件  <br />1：浏览跑步课程 <br />2：浏览跑步计划 <br />3：浏览睡眠  <br />4：睡眠呼吸 <br />5：点击设备体重管理入口 |
| year   | int      | 浏览日期 年                                                  |
| month  | int      | 浏览日期 月                                                  |
| day    | int      | 浏览日期 日                                                  |
| hour   | int      | 当天最后一次点击时间 时                                      |
| min    | int      | 当天最后一次点击时间 分                                      |
| sec    | int      | 当天最后一次点击时间 秒                                      |
| count  | int      | 点击次数                                                     |

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| type            | int      | 特性名称 <br />1：跑步课程 <br />2：跑步计划 <br />3：跑后拉伸 |
| evt             | int      | 事件 <br />1：使用跑步课程 <br />2：执行跑步计划<br />3：执行跑后拉伸 |
| start_year      | int      | 启动时间 年                                                  |
| start_month     | int      | 启动时间 月                                                  |
| start_day       | int      | 启动时间 日                                                  |
| start_hour      | int      | 启动时间 时                                                  |
| start_min       | int      | 启动时间 分                                                  |
| start_sec       | int      | 启动时间 秒                                                  |
| end_year        | int      | 结束时间 年                                                  |
| end_month       | int      | 结束时间 月                                                  |
| end_day         | int      | 结束时间 日                                                  |
| end_hour        | int      | 结束时间 时                                                  |
| end_min         | int      | 结束时间 分                                                  |
| end_sec         | int      | 结束时间 秒                                                  |
| completion_rate | int      | 点击次数  0到100                                             |

`示例：`

```c
{
    "browse_count":1,
    "implement_count":1,
    "bro_items":[
        {
            "type":0,
            "evt":0,
            "year":0,
            "month":0,
            "day":0,
            "hour":0,
            "min":0,
            "sec":0,
            "count":0
        }
    ],
    "imp_items":[
        "type":0,
        "evt":0,
        "start_year":0,
        "start_month":0,
        "start_day":0,
        "start_hour":0,
        "start_min":0,
        "start_sec":0,
        "end_year":0,
        "end_month":0,
        "end_day":0,
        "end_hour":0,
        "end_min":0,
        "end_sec":0,
        "completion_rate":0
    ]
}
```
