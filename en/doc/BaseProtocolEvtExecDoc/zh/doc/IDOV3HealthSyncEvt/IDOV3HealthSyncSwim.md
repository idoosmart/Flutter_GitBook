#### 同步游泳


**App收到的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| year                 | int      | 数据日期 年                                                  |
| month                | int      | 数据日期 月                                                  |
| day                  | int      | 数据日期 日                                                  |
| hour                 | int      | 数据日期 时                                                  |
| minute               | int      | 数据日期 分                                                  |
| second               | int      | 数据日期 秒                                                  |
| version              | int      | 协议版本号                                                   |
| type                 | int      | 类型 0 无效,1 为室内游泳,2 为开阔水域游泳                    |
| calories             | int      | 卡路里                                                       |
| distance             | int      | 距离,单位米                                                  |
| confirm_distance     | int      | 用户确认距离                                                 |
| duration             | int      | 时长,单位秒                                                  |
| trips                | int      | 游泳趟数                                                     |
| average_swolf        | int      | 平均swolf                                                    |
| total_strokes_number | int      | 总划水次数                                                   |
| swimming_posture     | int      | 主泳姿  0 : 混合泳 1 : 自由泳 2 : 蛙泳 4 : 其他  |
| pool_distance        | int      | 泳池距离 单位cm                                              |
| avg_speed            | int      | 平均配速<br />version=1有效,否则字段是0                      |
| avg_frequency        | Int      | 平均划水频率<br />version=1有效,否则字段是0                  |
| items                | 集合     | 游泳数据详情，swolf & strokesNumber & duration & swimmingPosture & distance & frequency & speed & stop_time & difference_time的集合 |

| 字段名           | 字段类型 | 字段说明                                          |
| ---------------- | -------- | ------------------------------------------------- |
| swolf            | int      | 划水效率                                          |
| strokes_number   | int      | 泳姿                                              |
| duration         | int      | 划水次数                                          |
| swimming_posture | int      | 时间,单位秒                                       |
| distance         | int      | 距离                                              |
| frequency        | int      | 频率<br />version=1有效,否则字段是0               |
| speed            | int      | 配速 公里/秒<br />version=1有效,否则字段是0       |
| stop_time        | int      | 结束时间<br />version=1有效,否则字段是0           |
| difference_time  | int      | 两趟之间的休息时间<br />version=1有效,否则字段是0 |

`示例：`

```c
{

}
```
