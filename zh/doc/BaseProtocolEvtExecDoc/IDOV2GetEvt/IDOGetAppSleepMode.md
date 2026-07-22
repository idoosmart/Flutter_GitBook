### 获取睡眠模式

功能表：supportAppSleepMode

**Flutter示例：**

```dart
/// 获取睡眠模式事件号
/// getAppSleepMode(
///   evtBase: _VBusEvtBase.base_app_get,
///   evtType: _VBusEvtType.app_get_app_sleep_mode),

/// 获取睡眠模式
libManager.send(evt: CmdEvtType.getAppSleepMode, json: jsonEncode({}));
```

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| sleep_mode_switch | int | 睡眠模式开关<br />1:开启<br />0:关闭<br />255:无效 |
| sleep_hour | int | 入睡时，0~23 |
| sleep_minute | int | 入睡分，0~59 |
| awake_hour | int | 起床时，0~23 |
| awake_minute | int | 起床分，0~59 |
| repeat | int | 重复周期<br />bit0 无效<br />bit1~bit7 对应周一至周日 |
| wake_alarm_repeat_cnt | int | 清醒闹钟重复次数，0~3 |
| wake_alarm_delay_time | int | 清醒闹钟提醒延迟，1~15 分钟 |

`示例：`

```json
{
  "sleep_mode_switch": 1,
  "sleep_hour": 22,
  "sleep_minute": 0,
  "awake_hour": 7,
  "awake_minute": 0,
  "repeat": 62,
  "wake_alarm_repeat_cnt": 3,
  "wake_alarm_delay_time": 10
}
```

**注意事项：**

- 下发前建议先判断功能表 `libManager.funTable.supportAppSleepMode`。
- 当 `sleep_mode_switch` 为 `255` 时表示无效/未知，建议业务侧按不支持处理。
- 协议 cmd/key：`02 4C`；事件号 `367`。
