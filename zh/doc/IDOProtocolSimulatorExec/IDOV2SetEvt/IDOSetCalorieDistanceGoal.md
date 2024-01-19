### 设置卡路里和距离目标(设置日常三环)


功能表：【setCalorieGoal，exMain3DistanceGoal(SDK待补充)，set_mid_high_time_goal_03_43(c库jsonid SDK待补充)，getSupportGetMainSportGoalV3，getSupportSetGetTimeGoalTypeV2】

**Flutter示例：**

```dart
/// 设置日常三环目标事件号
setCalorieDistanceGoal(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_calorie_distance_goal),

/// 设置日常三环目标
libManager.send(evt: CmdEvtType.setCalorieDistanceGoal, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名             | 字段类型 | 字段说明                                              |
| ------------------ | -------- | ----------------------------------------------------- |
| calorie            | int      | 活动卡路里目标 <br />单位千卡                         |
| distance           | int      | 距离 <br />单位米                                     |
| calorie_min        | int      | 活动卡路里最小值 <br />单位千卡                       |
| calorie_max        | int      | 活动卡路里最大值 <br />单位千卡                       |
| mid_high_time_goal | int      | 中高运动时长的目标 <br />单位秒                       |
| walk_goal_time     | int      | 目标时间<br />单位秒                                  |
| time_goal_type     | int      | 目标类型<br />0：无效 <br />1：日目标 <br />2：周目标 |

`示例：`

```c
{
   "calorie":500,
   "distance":200,
   "calorie_min":100,
   "calorie_max":666,
   "mid_high_time_goal":600,
   "walk_goal_time":600,
   "time_goal_type":0
}
```
