### 获取所有的健康监测开关


功能表:getHealthSwitchStateSupportV3

**Flutter示例：**

```dart
/// 获取所有的健康监测开关事件号
getAllHealthSwitchState(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_all_health_switch_state),

/// 获取所有的健康监测开关
libManager.send(evt: CmdEvtType.getAllHealthSwitchState, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                | 字段类型 | 字段说明                                                     |
| --------------------- | -------- | ------------------------------------------------------------ |
| heart_mode            | int      | 连续测量心率开关  <br />170是开，85是关                       |
| pressure_mode         | int      | 压力自动检测开关 <br />170是开，85是关                        |
| spo2_mode             | int      | 血氧自动检测开关 <br />170是开，85是关                        |
| science_mode          | int      | 科学睡眠开关     <br />170（科学睡眠）,85(普通睡眠)       |
| temperature_mode      | int      | 夜间体温开关    <br />170是开，85是关                         |
| noise_mode            | int      | 噪声开关    <br />170是开，85是关                             |
| menstrual_mode        | int      | 生理周期开关 <br />170是开，85是关                            |
| walk_mode             | int      | 走动提醒开关 <br />170是开，85是关                            |
| handwashing_mode      | int      | 洗手提醒开关 <br />170是开，85是关                            |
| drinkwater_mode       | int      | 喝水提醒开关 170是开，85是关                                  |
| heartmode_notify_flag | int      | 心率通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| pressure_notify_flag  | int      | 压力通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| spo2_notify_flag      | int      | 血氧通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| menstrual_notify_flag | int      | 生理周期通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| guidance_notify_flag  | int      | 健身指导通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| reminder_notify_flag  | int      | 提醒事项通知状态类型 <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| respir_rate_state     | int      | 呼吸率开关 <br />85：关闭   <br />170：开                 |
| body_power_state      | int      | 身体电量开关 <br />85：关闭   <br />170：开               |

`示例：`

```c
{
  "heart_mode" : 85,
  "pressure_mode" : 85,
  "spo2_mode" : 85,
  "science_mode" : 85,
  "temperature_mode" : 85,
  "noise_mode" : 85,
  "menstrual_mode" : 85,
  "walk_mode" : 85,
  "handwashing_mode" : 85,
  "drinkwater_mode" : 85,
  "heartmode_notify_flag" : 0,
  "pressure_notify_flag" : 0,
  "spo2_notify_flag" : 0,
  "menstrual_notify_flag" : 0,
  "guidance_notify_flag" : 0,
  "reminder_notify_flag" : 0,
  "respir_rate_state" : 0,
  "body_power_state" : 0
}
```
