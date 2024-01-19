#### 同步运动


**App收到的json字段**：

| 字段名                       | 字段类型 | 字段说明                                                     |
| ---------------------------- | -------- | ------------------------------------------------------------ |
| version                      | int      | 协议版本号 <br />0：没有佩戴标识数据<br />16：有佩戴标识数据,需要固件配置`v3SupportWearFlag`功能表 |
| year                         | int      | 数据日期 年                                                  |
| month                        | int      | 数据日期 月                                                  |
| day                          | int      | 数据日期 日                                                  |
| start_time                   | int      | 开始时间,单位分钟,距离0点的偏移                               |
| per_minute                   | int      | 每条数据产生的间隔 分钟 （15分钟默认）   <br />206定制新增：时长间隔 1分钟<br />产生间隔若为一分钟 需要app判断 `supportPerMinuteOne` 来判断固件是否支持一分钟同步类型 |
| total_step                   | int      | 总步数                                                       |
| total_rest_activity_calories | int      | 总活动+静息卡路里                                            |
| total_distances              | int      | 总距离  英里数据 = 固件距离（米）乘以0.00062                 |
| total_active_time            | int      | 当天的活动时间 单位分钟                                      |
| total_activity_calories      | int      | 总活动卡路里                                                 |
| walk_goal_time | int | 固件实际走动时长 需要配置  单位小时 |
| item_count                   | int      | 运动数据详情个数                                             |
| wear_flag_array | int [] | 24小时的每个小时的佩戴分钟数，最大24个字节<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |
| items                        | 集合     | 运动数据详情，`mode`&`step_count`&`active_time`&`activity_calories`&`distance`&`rest_activity_calories`的集合 |

| 字段名                 | 字段类型 | 字段说明                                                  |
| ---------------------- | -------- | --------------------------------------------------------- |
| mode                   | int      | 模式 00：安静， 01：轻微，10：中等活跃， 11：激烈         |
| step_count             | int      | 步数个数                                                  |
| active_time            | int      | 活跃时长 单位分钟， 最大`per_minute`参数决定 目前是15分钟 |
| activity_calories      | int      | 活动卡路里                                                |
| distance               | int      | 距离，单位米                                              |
| rest_activity_calories | int      | 活动+静息卡路里                                           |

`示例：`

```c
{
    "day" : 26,
      "item_count" : 47,
      "items" :
      [
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        }
      ],
      "month" : 12,
      "per_minute" : 15,
      "start_time" : 0,
      "total_active_time" : 0,
      "total_activity_calories" : 0,
      "total_distances" : 0,
      "total_rest_activity_calories" : 0,
      "total_step" : 0,
      "version" : 0,
      "walk_goal_time" : 0,
      "wear_flag_array" :
      [
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0
      ],
      "year" : 2022
}
```
