#### APP交换运动数据过程


**App下发的json字段**:

| 字段名   | 字段类型 | 字段说明                                                |
| -------- | -------- | ------------------------------------------------------- |
| day      | int      | 开始时间 日                                             |
| hour     | int      | 开始时间 时                                             |
| minute   | int      | 开始时间 分                                             |
| second   | int      | 开始时间 秒                                             |
| duration | int      | 持续时长 单位s                                          |
| calories | int      | 卡路里 单位大卡                                         |
| distance | int      | 距离 单位0.01km                                         |
| status   | int      | 0：全部有效<br />1：距离无效<br />2：gps信号弱 |


`示例：`

```c
{
    "day":26,
    "hour":10,
    "minute":46,
    "second":30,
    "duration":80,
    "calories":300,
    "distance":500,
    "status":0
}
```

**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明                                     |
| --------------- | -------- | -------------------------------------------- |
| status          | int      | 1:成功<br />2:设备没有进入运动模式失败 |
| step            | int      | 步数/次数                                    |
| calories        | int      | 卡路里 单位：大卡                            |
| distance        | int      | 距离 单位：0.01km                            |
| cur_hr_value    | int      | 心率数据<br />当前心率                       |
| interval_second | int      | 心率间隔 单位s                               |
| hr_value_serial | int      | 序列号                                       |
| hr_value        | int []   | 心率值数据                                   |

`示例：`

```c
{
    "status":1,
    "step":200,
    "calories":200,
    "distance":50,
    "cur_hr_value":80,
    "interval_second":5,
    "hr_value_serial":0,
    "hr_value":[
        85,
        86,
        90,
        79,
        88,
        92
    ]
}
```

