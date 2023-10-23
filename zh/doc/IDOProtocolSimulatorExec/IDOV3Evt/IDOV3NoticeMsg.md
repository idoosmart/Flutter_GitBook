### V3通知消息提醒


功能表:getNotifyMsgV3

**Flutter示例：**

```dart
/// 通知消息提醒事件号
noticeMessageV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_notice_message),

/// 通知消息提醒
libManager.send(evt: CmdEvtType.noticeMessageV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| verison           | int      | 协议库版本号默认version=1<br />version=2是增加msg_id的发送格式 |
| evt_type          | int      | 消息应用类型                                                 |
| msg_id            | int      | 消息的ID   <br />evt_type是消息提醒，起作用 mesg_ID 如果是0这个字段不起作 |
| support_answering | bool     | 支持接听 1 <br />不支持接听 0                                |
| support_mute      | bool     | 支持静音 1<br />不支持静音 0                                 |
| support_hang_up   | bool     | 支持挂断 1<br />不支持挂断 0                                 |
| contact           | char []  | 联系人名称 最大63个字节                                      |
| phone_number      | char []  | 电话号码 最大31个字节                                        |
| data_text         | char []  | 消息内容 最大249个字节                                       |

`示例：`

```c
{
    "verison":2,
    "evt_type":12289,
    "msg_id":1,
    "support_answering":false,
    "support_mute":false,
    "support_hang_up":false,
    "msg_data":"你好",
    "contact":"Lihua",
    "phone_number":"13340216580",
    "data_text":"123456"
}
```

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明         |
| ---------- | -------- | ---------------- |
| is_success | int      | 1：成功 ， 0失败 |

`示例：`

```c
{
  "is_success":1
}
```

