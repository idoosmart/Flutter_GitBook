### 获得固件三级版本和BT的3级版本


功能表:getBleAndBtVersion

**Flutter示例：**

```dart
/// 获得固件三级版本和bt的3级版本事件号
getFirmwareBtVersion(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_get_firmware_bt_version),

/// 获得固件三级版本和bt的3级版本
libManager.send(evt: CmdEvtType.getFirmwareBtVersion, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| firmware_version1 | int      | 固件版本version1                                             |
| firmware_version2 | int      | 固件版本version2                                             |
| firmware_version3 | int      | 固件版本version3                                             |
| BT_flag           | int      | BT版本生效标志位<br />0：无效<br />1：说明固件有对应的BT固件 |
| BT_version1       | int      | BT的版本version1                                             |
| BT_version2       | int      | BT的版本version2                                             |
| BT_version3       | int      | BT的版本version3                                             |
| BT_match_version1 | int      | BT的所需要匹配的版本version1                                 |
| BT_match_version2 | int      | BT的所需要匹配的版本version2                                 |
| BT_match_version3 | int      | BT的所需要匹配的版本version3                                 |

`示例：`

```c
{
  "BT_flag" : 1,
  "BT_match_version1" : 2,
  "BT_match_version2" : 0,
  "BT_match_version3" : 7,
  "BT_version1" : 2,
  "BT_version2" : 0,
  "BT_version3" : 9,
  "firmware_version1" : 2,
  "firmware_version2" : 0,
  "firmware_version3" : 6
}
```