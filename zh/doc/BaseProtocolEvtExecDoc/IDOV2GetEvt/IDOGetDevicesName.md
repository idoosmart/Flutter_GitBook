### ~~获取手表名字~~


功能表:TODO

**Flutter示例：**

```dart
/// 获取手表名字事件号
getDeviceName(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_devices_name),

/// 获取手表名字
libManager.send(evt: CmdEvtType.getDeviceName, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型  | 字段说明                                               |
| ---------- | --------- | ------------------------------------------------------ |
| is_success | int       | 1：成功 ， 0失败                                       |
| dev_name   | char [16] | 成功: 固件端目前保存的名字，设置的成功，返回设置的名字 |

`示例：`

```c
{
  "is_success":1,
  "dev_name":"ID208BT"
}
```
