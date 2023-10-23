### V3设备通知APP运动过程切换

功能表：setSupportSportPlan


**App下发的json字段**:

| 字段名      | 字段类型 | 字段说明                                                     |
| ----------- | -------- | ------------------------------------------------------------ |
| operate     | int      | 操作<br />1：开始运动 <br />2：暂停运动 <br />3：恢复运动 <br />4：结束运动 <br />5：切换动作 |
| type        | int      | 计划类型<br />1：跑步计划3km <br />2：跑步计划5km <br />3：跑步计划10km <br />4：半程马拉松训练（二期） <br />5：马拉松训练（二期） |
| action_type | int      | 动作类型  <br />1：快走<br />2：慢跑<br />3：中速跑<br />4：快跑 <br />5：结束课程运动（还要等待用户是否有自由运动）（此字段当operate为5起作用） |
| err_code    | int      | 0:成功   其他失败                                         |

`示例：`

```c
{
    "operate":1,
    "type":1,
    "action_type":1,
    "err_code":0
}
```

**App收到的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| operate      | int      | 1：开始运动 <br />2：暂停运动 <br />3：恢复运动 <br />4：结束运动<br />5：切换动作 |
| type         | int      | 计划类型<br />1：跑步计划3km<br />2：跑步计划5km <br />3：跑步计划10km <br />4：半程马拉松训练（二期）<br />5：马拉松训练（二期） |
| action_type  | int      | 动作类型  <br />1：快走<br />2：慢跑<br />3：中速跑<br />4：快跑  <br />5：结束课程运动 （还要等待用户是否有自由运动）；6课程结束后自由运动 （此字段当operate为5起作用） |
| year         | int      | 训练的课程日期(训练日的日期) 年                              |
| month        | int      | 训练的课程日期(训练日的日期) 月                              |
| day          | int      | 训练的课程日期(训练日的日期) 日                              |
| time         | int      | 动作目标时间  单位秒                                         |
| low_heart    | int      | 心率范围低值                                                 |
| height_heart | int      | 心率范围高值                                                 |
| cur_day      | int      | 开始/暂停/恢复/结束时间，由operate决定是什么时间类型<br />时间 日 |
| hour         | int      | 时间 时                                                      |
| minute       | int      | 时间 分                                                      |
| second       | int      | 时间 秒                                                      |


`示例：`

```c
{
    "operate":1,
    "type":1,
    "action_type":1,
    "year":2022,
    "month":12,
    "day":26,
    "time":200,
    "low_heart":80,
    "height_heart":110,
    "cur_day":1,
    "hour":0,
    "minute":0,
    "second": 0
}
```