### 获取通知中心开关


功能表:reminderAncs

**Flutter示例：**

```dart
/// 获取通知中心的状态事件号
getNoticeStatus(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_notice_status),

/// 获取通知中心的状态
libManager.send(evt: CmdEvtType.getNoticeStatus, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| notify_switch  | int      | 通知提醒开关<br />85：ble总开关开<br />170：总开关关<br />136：设置子开关<br />187：只开bt（开关）<br />204：ble、bt都开（开关）<br />0：无效 |
| call_switch    | int      | 来电子提醒开关 <br />85：开<br />170：关<br />0：无效  |
| notify_item1   | int      | 子应用开关1 每个bit代表一个应用                              |
| notify_item2   | int      | 子应用开关2 每个bit代表一个应用                              |
| call_delay     | int      | 来电提醒延时 单位秒                                          |
| notify_item3   | int      | 子应用开关3 每个bit代表一个应用                              |
| notify_item4   | int      | 子应用开关4 每个bit代表一个应用                              |
| notify_item5   | int      | 子应用开关5 每个bit代表一个应用                              |
| notify_item6   | int      | 子应用开关6 每个bit代表一个应用                              |
| notify_item7   | int      | 子应用开关7 每个bit代表一个应用                              |
| notify_item8   | int      | 子应用开关8 每个bit代表一个应用                              |
| notify_item9   | int      | 子应用开关9 每个bit代表一个应用                              |
| notify_item10  | int      | 子应用开关10 每个bit代表一个应用                             |
| msg_all_switch | int      | 消息应用总开关 <br />开：85 关：170                       |
| notify_item11  | int      | 子应用开关11 每个bit代表一个应用                             |
| notify_item12  | int      | 子应用开关12 每个bit代表一个应用                             |

`示例：`

```c
{
  "call_delay" : 0,
  "call_switch" : 85,
  "msg_all_switch" : 0,
  "notify_item1" : 0,
  "notify_item10" : 0,
  "notify_item11" : 0,
  "notify_item12" : 0,
  "notify_item2" : 0,
  "notify_item3" : 0,
  "notify_item4" : 0,
  "notify_item5" : 0,
  "notify_item6" : 0,
  "notify_item7" : 0,
  "notify_item8" : 0,
  "notify_item9" : 0,
  "notify_item10" : 0,
  "notify_switch" : 85,
  "notify_item11" : 0,
    "notify_item12" : 0
}
```
