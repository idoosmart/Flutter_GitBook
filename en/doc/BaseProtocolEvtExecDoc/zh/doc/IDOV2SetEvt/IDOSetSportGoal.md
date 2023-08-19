### 设置运动目标


功能表: 【supportWalkGoalSteps(SDK待补充)，v2SupportSetStepDataType(SDK待补充)】

**Flutter示例：**

```dart
/// 设置运动目标事件号
setSportGoal(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_sport_goal),

/// 设置运动目标
libManager.send(evt: CmdEvtType.setSportGoal, json: jsonEncode(json));
```

**App下发的json字段**：

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| sport_step      | int      | 步数                                                         |
| walk_goal_steps | int      | 每小时步数目标设置                                           |
| target_type     | int      | 周目标设置，0：无效 1：日目标 <br />2：周目标 需要功能表支持 |

`示例：`

```c
{
  "sport_step":2000,
  "walk_goal_steps":15,
  "target_type":23
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

