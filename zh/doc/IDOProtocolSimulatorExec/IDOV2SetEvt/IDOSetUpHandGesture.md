### 设置抬腕亮屏


功能表：getUpHandGesture

**Flutter示例：**

```dart
/// 抬手亮屏事件号
setUpHandGesture(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_up_hand_gesture),

/// 抬手亮屏
libManager.send(evt: CmdEvtType.setUpHandGesture, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名         | 字段类型 | 字段说明                               |
| -------------- | -------- | -------------------------------------- |
| on_off         | int      | 开关<br />1 开 <br />0 关              |
| show_second    | int      | 亮屏时间 单位秒                        |
| has_time_range | int      | 是否有时间范围<br />1：有<br />0：没有 |
| start_hour     | int      | 开始时间 时                            |
| start_minute   | int      | 开始时间 分                            |
| end_hour       | int      | 结束时间 时                            |
| end_minute     | int      | 结束时间 分                            |

`示例：`

```json
{
  "on_off":1,
  "show_second":10,
  "has_time_range":1,
  "start_hour":8,
  "start_minute":0,
  "end_hour":18,
  "end_minute":0
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```json
{
  "status_code":0
}
```

