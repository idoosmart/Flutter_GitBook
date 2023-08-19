### 设置健身指导开关


功能表：setSetFitnessGuidance

**Flutter示例：**

```dart
/// 健身指导1.C库事件
setFitnessGuidance(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_fitness_guidance),

/// 健身指导
libManager.send(evt: CmdEvtType.setFitnessGuidance, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| mode         | int      | 健身指导模式开关 <br />170开<br />85关闭                  |
| start_hour   | int      | 开始时间 时                                                  |
| start_minute | int      | 开始时间 分                                                  |
| end_hour     | int      | 结束时间 时                                                  |
| end_minute   | int      | 结束时间 分                                                  |
| notify_flag  | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 uint8_t repeat; //   uint32_t target_steps;//目标步数 |
| go_mode      | int      | 走动提醒开关 <br />170开<br />85关闭                      |
| repeat       | int      | 重复<br />bit0：无效<br />bit1-7分别对应周一到周天           |
| target_steps | int      | 目标步数                                                     |

`示例：`

```c
{
  "mode":85,
    "start_hour":9,
    "start_minute":0,
    "end_hour":18,
    "end_minute":0,
    "notify_flag":1,
    "go_mode":85,
    "repeat":127,
    "target_steps":2000
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`
```c
{
  "is_success":0
}
```
