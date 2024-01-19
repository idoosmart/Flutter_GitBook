### 获取BT名称


功能表:getBtAddrV2

**Flutter示例：**

```dart
/// 获取bt蓝牙名称事件号
getBtName(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_bt_name)

/// 获取bt蓝牙名称
libManager.send(evt: CmdEvtType.getBtName, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名  | 字段类型  | 字段说明                                                     |
| ------- | --------- | ------------------------------------------------------------ |
| bt_name | char [32] | bt蓝牙名称<br />需要固件开启v2_get_bt_addr 且 alarm_count>0才会返回bt名称，否则返回空 |

`示例：`

```c
{
  "bt_name" : "ID206"
}
```
