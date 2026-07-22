### 获取固件本地保存联系人文件修改时间


功能表:TODO

**Flutter示例：**

```dart
/// 获取固件本地保存联系人文件修改时间事件号
getContactReviseTime(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_contact_revice_time
),

/// 获取固件本地保存联系人文件修改时间
libManager.send(evt: CmdEvtType.getContactReviseTime, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| result | int      | 0：不需要下发联系人文件    <br />1：需要下发联系人数据 |


`示例：`

```c
{
    "result":0
}
```
