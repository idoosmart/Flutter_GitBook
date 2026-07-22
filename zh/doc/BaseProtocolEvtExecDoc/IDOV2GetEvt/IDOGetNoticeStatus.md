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
| notify_switch  | int      | 通知提醒开关<br />0：总开关关(预留 无效功能)<br />1：ble总开关开(发起配对 IOS专用)<br />2：设置子开关<br />3：只开bt（开关）<br />4：ble、bt都开（开关）<br />-1：无效 |
| call_switch    | int      | 来电子提醒开关 <br />1:开<br />0:关<br />-1:无效             |
| notify_item1   | int      | 子应用开关1，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item2   | int      | 子应用开关2，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| call_delay     | int      | 来电提醒延时 单位秒                                          |
| notify_item3   | int      | 子应用开关3，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item4   | int      | 子应用开关4，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item5   | int      | 子应用开关5，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item6   | int      | 子应用开关6，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item7   | int      | 子应用开关7，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item8   | int      | 子应用开关8，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item9   | int      | 子应用开关9，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item10  | int      | 子应用开关10，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| msg_all_switch | int      | 消息应用总开关 <br />1:开<br />0:关<br />-1:无效(不支持)     |
| notify_item11  | int      | 子应用开关11，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item12  | int      | 子应用开关12，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item13  | int      | 子应用开关13，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item14  | int      | 子应用开关14，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item15  | int      | 子应用开关15，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |
| notify_item16  | int      | 子应用开关16，详细定义请参考 [通知中心子开关 bit 位说明](../../IDOV2NoticeItemIntroduction.md) |

`示例：`

```json
{
  "call_delay" : 0,
  "call_switch" : 1,
  "msg_all_switch" : 0,
  "notify_item1" : 0,
  "notify_item2" : 0,
  "notify_item3" : 0,
  "notify_item4" : 0,
  "notify_item5" : 0,
  "notify_item6" : 0,
  "notify_item7" : 0,
  "notify_item8" : 0,
  "notify_item9" : 0,
  "notify_item10" : 0,
  "notify_item11" : 0,
  "notify_item12" : 0,
  "notify_item13" : 0,
  "notify_item14" : 0,
  "notify_item15" : 0,
  "notify_item16" : 0,
  "notify_switch" : 1
}
```
