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
| time_zone         | int      | 时区扩大 100 倍返回，如时区 8 对应 800，5.5 对应 550<br />仅当 `supportSyncHealthDataWithTimeZone` 功能表开启时有效 |
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
  "average_swolf": 0,
  "avg_frequency": 0,
  "avg_speed": 0,
  "calories": 0,
  "confirm_distance": 0,
  "day": 12,
  "distance": 0,
  "duration": 83,
  "hour": 9,
  "items": [
    {
      "swolf": 32,
      "swimming_posture": 1,
      "strokes_number": 111,
      "duration": 100,
      "distance": 35,
      "frequency": 1,
      "speed": 5,
      "stop_time": 5,
      "difference_time": 2
    }
  ],
  "minute": 18,
  "month": 1,
  "pool_distance": 25,
  "pool_distance_decimal": 0,
  "second": 15,
  "swimming_posture": 0,
  "total_strokes_number": 0,
  "trips": 0,
  "type": 1,
  "version": 1,
  "year": 2026
}
```
