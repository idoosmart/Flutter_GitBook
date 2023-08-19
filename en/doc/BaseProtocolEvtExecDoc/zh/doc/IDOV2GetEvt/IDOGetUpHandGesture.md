### 获取抬腕数据


功能表:getUpHandGestureEx

**Flutter示例：**

```dart
/// 获取抬腕数据事件号
getUpHandGesture(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_up_hand_gesture),

/// 获取抬腕数据
libManager.send(evt: CmdEvtType.getUpHandGesture, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名         | 字段类型 | 字段说明                                    |
| -------------- | -------- | ------------------------------------------- |
| on_off         | int      | 开关<br />170 开<br />85 关              |
| show_second    | int      | 亮屏时间 <br />单位秒                       |
| has_time_range | int      | 是否有时间范围,<br />1 有<br />0 没有 |
| start_hour     | int      | 开始时间 时                                 |
| start_minute   | int      | 开始时间 分                                 |
| end_hour       | int      | 结束时间 时                                 |
| end_minute     | int      | 结束时间 分                                 |

`示例：`

```c
{
  "end_hour" : 0,
  "end_minute" : 0,
  "has_time_range" : 0,
  "on_off" : 170,
  "show_second" : 5,
  "start_hour" : 0,
  "start_minute" : 0
}
```

