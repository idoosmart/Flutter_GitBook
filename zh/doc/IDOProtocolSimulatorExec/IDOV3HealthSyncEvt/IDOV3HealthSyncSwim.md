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
| calories             | int      | 卡路里<br />单位:Kcal                                        |
| distance             | int      | 距离<br />单位:米                                            |
| confirm_distance     | int      | 用户确认距离<br />单位:米                                    |
| duration             | int      | 时长<br />单位:秒                                            |
| trips                | int      | 游泳趟数                                                     |
| average_swolf        | int      | 平均划水效率                                                 |
| total_strokes_number | int      | 总划水次数                                                   |
| swimming_posture     | int      | 主泳姿  <br />0 : 混合泳 <br />1 : 自由泳 <br />2 : 蛙泳 <br />3 : 仰泳<br />4 : 蝶泳 |
| pool_distance        | int      | 泳池距离<br />单位:米                                        |
| avg_speed            | int      | 平均配速<br />秒/百米 一百米用了多少秒 <br />单位:秒<br />version=1有效,否则字段是0 |
| avg_frequency        | Int      | 平均划水频率<br />单位:次/分<br />version=1有效,否则字段是0  |
| items                | 集合     | 游泳数据详情，`swolf` & `strokesNumber` & `duration` & `swimmingPosture` & `distance` & `frequency `& `speed` & `stop_time` & `difference_time`的集合 |

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| swolf            | int      | 划水效率                                                     |
| swimming_posture | int      | 泳姿<br />0 : 混合泳 <br />1 : 自由泳 <br />2 : 蛙泳 <br />3 : 仰泳<br />4 : 蝶泳 |
| strokes_number   | int      | 划水次数                                                     |
| duration         | int      | 时间<br />单位:秒                                            |
| distance         | int      | 距离<br />单位:米                                            |
| frequency        | int      | 频率<br />单位:次/分<br />version=1有效,否则字段是0          |
| speed            | int      | 配速<br />秒/百米 一百米用了多少秒 <br />单位:秒<br />version=1有效,否则字段是0 |
| stop_time        | int      | 结束时间<br />单位:秒<br />version=1有效,否则字段是0         |
| difference_time  | int      | 两趟之间的休息时间<br />单位:秒<br />version=1有效,否则字段是0 |

`示例：`

```c
{

}
```
