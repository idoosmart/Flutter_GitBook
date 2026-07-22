### 获取设置的卡路里/距离/中高运动时长


功能表:getSupportGetMainSportGoalV3 【setCalorieGoal，exMain3DistanceGoal(待补充)，setMidHighTimeGoal，getSupportSetGetTimeGoalTypeV2】

**Flutter示例：**

```dart
/// 获取设置的卡路里/距离/中高运动时长事件号
getMainSportGoal(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_main_sport_goal),

/// 获取设置的卡路里/距离/中高运动时长
libManager.send(evt: CmdEvtType.getMainSportGoal, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| time_goal_type | int      | 0：无效 <br />1：日目标 <br />2：周目标  <br />需要固件开启功能表 `getSupportSetGetTimeGoalTypeV2` |

**App收到的json字段**：

| 字段名             | 字段类型 | 字段说明                                                     |
| ------------------ | -------- | ------------------------------------------------------------ |
| calorie            | int      | 活动卡路里目标  单位千卡<br />需要固件开启功能表 `setCalorieGoal` |
| distance           | int      | 距离 单位米                                                  |
| calorie_min        | int      | 活动卡路里最小值                                             |
| calorie_max        | int      | 活动卡路里最大值                                             |
| mid_high_time_goal | int      | 中高运动时长的目标 <br />单位秒<br />需要固件开启功能表`setMidHighTimeGoal` |
| walk_goal_time     | int      | 目标时间<br />单位秒                                         |
| time_goal_type     | int      | 0：无效 1：日目标 2：周目标<br />需要固件开启功能表 `getSupportSetGetTimeGoalTypeV2` |

`示例：`

```c
{
  "calorie" : 4,
  "distance" : 200,
  "calorie_min" : 101,
  "calorie_max" : 500,
  "mid_high_time_goal" : 1,
  "walk_goal_time" : 1,
  "time_goal_type" : 1,
}
```

