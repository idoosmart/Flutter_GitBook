#### 同步睡眠

**App收到的json字段**：

| 字段名                      | 字段类型 | 字段说明                                                     |
| --------------------------- | -------- | ------------------------------------------------------------ |
| data_type                   | int      | 1:科学睡眠（有REM、呼吸得分）<br />2:午睡  <br />4:普通睡眠<br />6:午睡且不支持科学睡眠 |
| fall_asleep_year            | int      | 入睡时间 年                                                  |
| fall_asleep_month           | int      | 入睡时间 月                                                  |
| fall_asleep_day             | int      | 入睡时间 日                                                  |
| fall_asleep_hour            | int      | 入睡时间 时                                                  |
| fall_asleep_minte           | int      | 入睡时间 分                                                  |
| get_up_year                 | int      | 起床时间 年                                                  |
| get_up_month                | int      | 起床时间 月                                                  |
| get_up_day                  | int      | 起床时间 日                                                  |
| get_up_hour                 | int      | 起床时间 时                                                  |
| get_up_minte                | int      | 起床时间分                                                   |
| total_sleep_time_mins       | int      | 睡眠总时长  单位：分                                         |
| wake_mins                   | int      | 总清醒时长  单位：分                                         |
| light_mins                  | int      | 总浅眠时长  单位：分                                         |
| rem_mins                    | int      | 总眼动时长  单位：分                                         |
| deep_mins                   | int      | 总深眠时长  单位：分                                         |
| wake_count                  | int      | 清醒次数                                                     |
| light_count                 | int      | 浅眠次数                                                     |
| rem_count                   | int      | 眼动次数                                                     |
| deep_count                  | int      | 深眠次数                                                     |
| awrr_status                 | int      | 呼吸状况                                                     |
| sleep_score                 | int      | 睡眠得分                                                     |
| breath_quality              | int      | 呼吸质量 （0 - 100） 无单位                                  |
| sleep_avg_hr_value          | int      | 睡眠阶段的心率平均值                                         |
| sleep_avg_spo2_value        | int      | 睡眠阶段的血氧平均值                                         |
| sleep_avg_respir_rate_value | int      | 睡眠阶段的呼吸率平均值                                       |
| item_count                  | int      | 睡眠详情个数                                                 |
| items                       | 集合     | 睡眠详情，`stage` & `duration`的集合                         |

| 字段名   | 字段类型 | 字段说明                                               |
| -------- | -------- | ------------------------------------------------------ |
| stage    | int      | 阶段 <br />1:醒着<br />2:浅睡<br />3:深睡 <br />4:眼动 |
| duration | int      | 时长 单位秒                                            |

`示例：`

```c
{
    "awrr_status" : 0,
    "breath_quality" : 0,
    "data_type" : 1,
    "deep_count" : 0,
    "deep_mins" : 0,
    "fall_asleep_day" : 0,
    "fall_asleep_hour" : 0,
    "fall_asleep_minte" : 0,
    "fall_asleep_month" : 0,
    "fall_asleep_year" : 0,
    "get_up_day" : 0,
    "get_up_hour" : 0,
    "get_up_minte" : 0,
    "get_up_month" : 0,
    "get_up_year" : 0,
    "item_count" : 0,
    "items" : null,
    "light_count" : 0,
    "light_mins" : 0,
    "rem_count" : 0,
    "rem_mins" : 0,
    "sleep_score" : 0,
    "total_sleep_time_mins" : 0,
    "wake_count" : 0,
    "wake_mins" : 0
}
```
