### V3APP下发跑步计划(运动计划)


功能表:setSupportSportPlan

**Flutter示例：**

```dart
/// app下发跑步计划(运动计划)事件号
setSendRunPlan(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_send_run_plan),

/// app下发跑步计划(运动计划)
libManager.send(evt: CmdEvtType.setSendRunPlan, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名  | 字段类型 | 字段说明                                                     |
| ------- | -------- | ------------------------------------------------------------ |
| verison | int      | 协议库版本号                                                 |
| operate | int      | 操作<br />1：开始计划 <br />2：计划数据下发 <br />3：结束计划 <br />4：查询跑步计划 |
| type    | int      | 计划类型<br />1：跑步计划3km <br />2：跑步计划5km <br />3：跑步计划10km<br />4：半程马拉松训练（二期）<br />5：马拉松训练（二期） |
| year    | int      | 计划开始时间 年                                              |
| month   | int      | 计划开始时间 月                                              |
| day     | int      | 计划开始时间 日                                              |
| hour    | int      | 计划开始时间 时                                              |
| min     | int      | 计划开始时间 月                                              |
| sec     | int      | 计划开始时间 日                                              |
| day_num | int      | 计划天数个数<br />当operate 为2时起作用                      |
| items   | 集合     | 计划详情 ` type` & `num` & `item`的集合                      |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| type   | int      | 训练类型 <br />186：计划休息 <br />187：计划户外跑步 <br />188：计划室内跑步<br />189：计划室内健身 |
| num    | int      | 动作个数<br />注：休息时动作个数为零 ，其他动作时个数不为零  |
| item   | 集合      | 动作详情  `type` &`time` & `height_heart `& `low_heart`的集合 |

| 字段名       | 字段类型 | 字段说明                                            |
| ------------ | -------- | --------------------------------------------------- |
| type         | int      | 动作类型<br /> 1：快走  2：慢跑  3：中速跑  4：快跑 |
| time         | int      | 目标时间  <br />单位秒                              |
| height_heart | int      | 心率范围低值                                        |
| low_heart    | int      | 心率范围高值                                        |

`示例：`

```c
{
  "verison":0,
    "operate":1,
    "type":1,
    "year":2022,
    "month":12,
    "day":26,
    "hour":17,
    "min":36,
    "sec":0,
    "day_num":1,
    "items":[
        {
         "type":186,
         "num":2,
         "item":[
            {
                "type":1,
                "time":200,
                "height_heart":110,
                "low_heart":80
            },
            {
                "type":1,
                "time":500,
                "height_heart":110,
                "low_heart":80
            }
         ]
        }
    ],
    "item":[],
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| err_code | int      | 00:成功，01:失败 ，02:已开启另一跑步计划                     |
| version  | int      | 协议库版本号                                                 |
| operate  | int      | 操作：<br />1：开始计划 <br />2：计划数据下发 <br />3：结束计划 <br />4：查询跑步计划 |
| type     | int      | 计划类型：<br />1：跑步计划3km <br />2：跑步计划5km <br />3：跑步计划10km <br />4：半程马拉松训练（二期）<br />5：马拉松训练（二期） |
| year     | int      | 计划实施开始时间 年                                          |
| month    | int      | 计划实施开始时间 月                                          |
| day      | int      | 计划实施开始时间 日                                          |
| hour     | int      | 计划实施开始时间 时                                          |
| min      | int      | 计划实施开始时间 分                                          |
| sec      | int      | 计划实施开始时间 秒                                          |

`示例：`

```c
{
    "err_code":0,
    "version":0,
    "operate":1,
    "type":1,
    "year":2022,
    "month":12,
    "day":26,
    "hour":17,
    "min":36,
    "sec":0
}
```

