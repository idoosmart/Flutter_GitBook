### 获取固件支持的详情最大设置数量


功能表:getSetMaxItemsNum

**Flutter示例：**

```dart
/// 获取固件支持的详情最大设置数量事件号
getSupportMaxSetItemsNum(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_support_max_set_items_num
),

/// 获取固件支持的详情最大设置数量
libManager.send(evt: CmdEvtType.getSupportMaxSetItemsNum, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名               | 字段类型 | 字段说明                                           |
| -------------------- | -------- | -------------------------------------------------- |
| contact_max_set_num  | int      | 常用联系人 固件支持app下发最大设置数量 0默认10个   |
| reminder_max_set_num | int      | 日程提醒     固件支持app下发最大设置数量 0默认30条 |
| msg_max_buff_size    | int      | 消息提醒最大发送缓存大小 0默认250字节              |

`示例：`

```c
{
    "contact_max_set_num":0,
    "reminder_max_set_num":0,
    "msg_max_buff_size":300,
}
```
