### V3通知消息提醒(动态)


**Flutter示例：**

```dart
/// V3动态消息通知事件号
setNoticeAppName(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_notice_message_add_app_name
)

/// V3动态消息通知
libManager.send(evt: CmdEvtType.setNoticeAppName, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| verison       | int      | 协议库版本号                                                 |
| os_platform   | int      | 系统<br />0 ：无效 ，1：安卓 ，2：ios                        |
| evt_type      | int      | 当前处于那种模式  <br />0：无效， 1：消息提醒                |
| notify_type   | int      | 消息的枚举类型 <br />上限值：20000                          |
| msg_ID        | int      | 消息的ID   <br />evt_type是消息提醒，起作用 mesg_ID 如果是0这个字段不起作用 |
| app_items_len | int      | 国家及语言详情的个数                                         |
| contact       | char []  | 联系人名称 最大64个字节                                      |
| phone_number  | char []  | 电话号码 最大32个字节                                        |
| msg_data      | char []  | 消息内容 最大250个字节                                       |
| items         | 集合     | 国家及语言详情<br />language & name的集合                    |

| 字段名   | 字段类型 | 字段说明                       |
| -------- | -------- | ------------------------------ |
| language | int      | 语言类型                       |
| name     | char []  | 国家对应的app名称 最大50个字节 |

`示例：`

```c
{
  "verison":0,
    "os_platform":1,
    "evt_type":1,
    "notify_type":3,
    "msg_ID":1,
    "app_items_len":1,
    "contact":"张三",
    "phone_number":"13425165412",
    "msg_data":"你好",
    "items":[
        {
            "language":2,
            "name":"wechar"
        }
    ]
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
