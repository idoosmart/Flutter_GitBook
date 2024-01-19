### V3多运动数据最后一次数据获取

功能表：syncV3ActivityExchangeData 【syncExchangeDataReplyAddRealTimeSpeedPaceV3，setSupportSportPlan，supportSmartCompetitor】

**Flutter示例：**

```dart
/// app获取v3运动数据事件号
exchangeAppGetActivityData(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_activity_data),

/// app获取v3运动数据
libManager.send(evt: CmdEvtType.exchangeAppGetActivityData, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                  | 字段类型 | 字段说明                                                     |
| ----------------------- | -------- | ------------------------------------------------------------ |
| version                 | int      | 协议库版本号默认16<br />功能表`setSupportSportPlan`开启后version=32 <br />功能表`syncExchangeDataReplyAddRealTimeSpeedPaceV3`开启后version=48 |
| type                    | int      | 运动类型                                                     |
| year                    | int      | 年                                                           |
| month                   | int      | 月                                                           |
| day                     | int      | 日                                                           |
| hour                    | int      | 时                                                           |
| minute                  | int      | 分                                                           |
| second                  | int      | 秒                                                           |
| hr_data_interval_minute | int      | 心率间隔 <br />单位分钟                                      |
| step                    | int      | 步数                                                         |
| durations               | int      | 持续时间<br />单位秒                                     |
| calories                | int      | 卡路里<br />单位kcal                                         |
| distance                | int      | 距离<br />单位米                                                |
| burn_fat_mins           | int      | 脂肪燃烧的心率持续时间<br />单位分钟                         |
| aerobic_mins            | int      | 有氧运动的持续时间                                           |
| limit_mins              | int      | 极限锻炼的持续时间                                           |
| warm_up                 | int      | 热身运动(字段重复)   预留                                    |
| fat_burning             | int      | 脂肪燃烧 (字段重复)  预留                                    |
| aerobic_exercise        | Int      | 有氧运动(字段重复)   预留                                    |
| anaerobic_exercise      | int      | 无氧运动(字段重复)   预留                                    |
| extreme_exercise        | int      | 极限锻炼(字段重复)   预留                                    |
| warm_up_time            | int      | 热身运动的累计时长 <br />单位秒                              |
| fat_burning_time        | int      | 脂肪燃烧的累计时长 <br />单位秒                              |
| aerobic_exercise_time   | int      | 有氧运动的累计时长<br />单位秒                               |
| anaerobic_exercise_time | int      | 无氧运动的累计时长 <br />单位秒                              |
| extreme_exercise_time   | int      | 极限锻炼的累计时长 <br />单位秒                              |
| avg_speed               | int      | 平均速度 <br />单位km/h                                      |
| max_speed               | int      | 最快速度 <br />单位km/h                                      |
| avg_step_stride         | int      | 平均步幅<br />单位:厘米                                     |
| max_step_stride         | int      | 最大步幅<br />单位:厘米                                          |
| km_speed                | int      | 平均公里配速<br />每公里耗时秒数                                    |
| fast_km_speed           | int      | 最快公里配速<br />每公里耗时秒数                                    |
| avg_step_frequency      | int      | 平均步频<br />单位:步/分钟                                       |
| max_step_frequency      | int      | 最大步频<br />单位:步/分钟                            |
| avg_hr_value            | int      | 平均心率<br />单位:BPM                                  |
| max_hr_value            | int      | 最大心率<br />单位:BPM                                         |
| km_speed_count          | int      | 公里配速详情个数 <br />最大100                               |
| steps_frequency_count   | int      | 步频详情个数                                                 |
| mi_speed_count          | int      | 英里配速个数<br />最大100                                    |
| recover_time            | int      | 恢复时长<br />单位小时<br />app收到该数据之后，每过一小时需要自减一 |
| vo2max                  | int      | 最大摄氧量 <br />单位 ml/kg/min                              |
| training_effect         | int      | 训练效果<br />范围： 1.0 - 5.0 （扩大10倍传输）              |
| grade                   | int      | 摄氧量等级  <br />1：低等  2：业余   3：一般  4：平均    5：良好  6：优秀   7：专业 |
| act_type | int | 计划类型：<br />1：跑步计划3km <br />2：跑步计划5km <br />3：跑步计划10km <br />4：半程马拉松训练（二期）<br />5：马拉松训练（二期）<br />64：6分钟轻松跑 <br />65：10分钟轻松跑 <br />66：15分钟轻松跑 <br />67：走跑结合初级 <br />68：走跑结合进阶 <br />69：走跑结合强化 <br />128：跑后拉伸 |
| training_offset | int | 训练的课程日期偏移 从零开始<br />version=32 字段有效 否则无效上报0 |
| action_data_count | int | 本次动作训练个数<br />version=32 字段有效 否则无效上报0 |
| in_class_calories | int | 课程内运动热量 单位千卡<br />version=32 字段有效 否则无效上报0 |
| completion_rate | int | 动作完成率 0—100<br />version=32 字段有效 否则无效上报0 |
| hr_completion_rate | int | 心率控制率 0—100<br />version=32 字段有效 否则无效上报0 |
| smart_competitor | int | 0:无效 1:非智能陪跑运动 2:智能陪跑运动<br />功能表`supportSmartCompetitor`开启有效 否则无效上报0 |
| ai_image_id      | int | ai形象ID<br />功能表`supportSmartCompetitor`开启有效 否则无效上报0 |
| user_image_id | int | 用户形象ID<br />功能表`supportSmartCompetitor`开启有效 否则无效上报0 |
| bg_image_id | int | 背景形象ID<br />功能表`supportSmartCompetitor`开启有效 否则无效上报0 |
| smart_competitor_pace | int | 智能陪跑对手配速<br />功能表`supportSmartCompetitor`开启有效 否则无效上报0 |
| real_speed_count        | int      | 实时速度个数<br /> version=48 字段有效 否则无效上报0 |
| pace_speed_count        | int      | 实时配速数组<br />version=48 字段有效 否则无效上报0                  |
| km_speed_s              | int []    | 每公里耗时秒数 配速                                          |
| steps_frequency         | int []    | 步频 <br />单位步/分钟                                       |
| items_mi_speed          | int []    | 英里配速数组 <br />s钟数据传输 一英里用了多少s               |
| item_real_speed         | int []    | 实时速度 <br />5s一个最大保存6小时 单位km/h<br />version=48 字段有效 否则无效上报0 |
| pace_speed_items        | int []    | 实时配速数组  <br />传过来的是 s 钟  每5S算一次<br />version=48 字段有效 否则无效上报0 |
| items | 集合 | 动作完成内容详情 `type`&`heart_con_value`&`time`&`goal_timegoal_time`的集合<br />version=32 字段有效 否则无效上报0 |

| 字段名             | 字段类型 | 字段说明                                                     |
| ------------------ | -------- | ------------------------------------------------------------ |
| type               | int      | 动作类型 <br />1快走 2慢跑 3中速跑 4快跑<br />version=32 字段有效 否则无效上报0 |
| heart_con_value    | int      | 每个动作心率控制<br />version=32 字段有效 否则无效上报0    |
| time               | int      | 动作完成时间 单位秒<br />version=32 字段有效 否则无效上报0 |
| goal_timegoal_time | int      | 动作目标时间<br />version=32 字段有效 否则无效上报0        |

`示例：`

```json
{
    "version":0,
    "type":0,
    "year":0,
    "month":0,
    "day":0,
    "hour":0,
    "minute":0,
    "second":0,
    "hr_data_interval_minute":0,
    "step":0,
    "durations":0,
    "calories":0,
    "distance":0,
    "burn_fat_mins":0,
    "aerobic_mins":0,
    "limit_mins":0,
    "warm_up":0,
    "fat_burning":0,
    "aerobic_exercise":0,
    "anaerobic_exercise":0,
    "extreme_exercise":0,
    "warm_up_time":0,
    "fat_burning_time":0,
    "aerobic_exercise_time":0,
    "anaerobic_exercise_time":0,
    "extreme_exercise_time":0,
    "avg_speed":0,
    "max_speed":0,
    "avg_step_stride":0,
    "max_step_stride":0,
    "km_speed":0,
    "fast_km_speed":0,
    "avg_step_frequency":0,
    "max_step_frequency":0,
    "avg_hr_value":0,
    "max_hr_value":0,
    "km_speed_count":0,
    "steps_frequency_count":0,
    "mi_speed_count":0,
    "recover_time":0,
    "vo2max":0,
    "training_effect":0,
    "grade":0,
    "act_type":0,
    "training_offset":0,
    "action_data_count":0,
    "in_class_calories":0,
    "completion_rate":0,
    "hr_completion_rate":0,
    "real_speed_count":0,
    "pace_speed_count":0,
    "km_speed_s":[],
    "steps_frequency":[],
    "items_mi_speed":[],
    "item_real_speed":[],
    "pace_speed_items":[],
    items:[
        {
            "type":0,
            "heart_con_value":0,
            "time":0,
            "goal_timegoal_time":0
        },
        {
            "type":0,
            "heart_con_value":0,
            "time":0,
            "goal_timegoal_time":0
        }
    ]
}
```