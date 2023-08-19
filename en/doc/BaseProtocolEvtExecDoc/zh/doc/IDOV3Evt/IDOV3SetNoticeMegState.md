### V3设置单个应用的通知状态


功能表:setSetNotificationStatus

**Flutter示例：**

```dart
/// v3 设置消息通知状态事件号
setNoticeMessageState(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.tran_json_set_notice_message_state),

/// v3 设置消息通知状态
libManager.send(evt: CmdEvtType.setNoticeMessageState, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| version        | int      | 协议库版本号                                                 |
| items_num      | int      | 消息详情的个数                                               |
| operat         | int      | 操作<br />1：增加 , 2：修改 , 3：获取查询                    |
| all_on_off     | int      | 增加、修改有效<br />消息通知总开关  170:开启总通知开关， 85:关闭总通知开关 |
| all_send_num   | int      | 发送的总包数 如果是发大于100的分次发送 <br />all_send_num=now_send_index 发送完成 |
| now_send_index | int      | 当前发送的序列                                               |
| items          | 集合     | 消息详情<br />evt_type & notify_state & pic_flag的集合       |

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| evt_type     | int      | 事件类型                                                     |
| notify_state | int      | 通知状态  <br />1：允许通知，2：静默通知 ， 3：关闭通知      |
| pic_flag     | int      | 回复的时候起作用，设置这个参数填0<br /> 0：无效  1：有下载对应的图片  2：没有对应的图片 |

`示例：`

```c
{
  "version": 0,
  "items_num": 0,
  "operat": 3,
  "all_on_off": 170,
  "all_send_num": 1,
  "now_send_index": 1,
  "items": null
}
```

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| version    | int      | 协议库版本号                                                 |
| err_code   | int      | 错误码 0成功，非0失败                                        |
| operat     | int      | 操作<br />1：增加，2：修改，3：获取查询                      |
| all_on_off | int      | 查询时有效<br />回复消息通知总开关状态 <br />170:开启总通知开关， 85:关闭总通知开关 |
| items_num  | int      | 查询时有效<br />固件目前有的消息详情items的个数              |
| items      | 集合     | 消息详情内容，查询时有效                                     |

| 字段名       | 字段类型 | 字段说明                                                 |
| ------------ | -------- | -------------------------------------------------------- |
| evt_type     | int      | 事件类型                                                 |
| notify_state | int      | 通知状态  <br />1：允许通知，2：静默通知，3：关闭通知    |
| pic_flag     | int      | 0：无效，1：有下载对应的图片，2：没有对应的图片 |

`示例：`

```c
{
  "version": 0,
  "err_code": 0,
  "operat": 3,
  "all_on_off": 170,
  "items_num": 2,
  "items": [
    {
        "evt_type": 1,
        "notify_state": 1,
        "pic_flag": 1
    },
    {
        "evt_type": 1,
        "notify_state": 1,
        "pic_flag": 1
    }
  ]
}
```
