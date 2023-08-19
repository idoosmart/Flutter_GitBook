### 查询获取bt配对开关、连接、a2dp连接、hfp连接状态(仅支持带bt蓝牙的设备)


功能表:getBleAndBtVersion

**Flutter示例：**

```dart
/// 查询bt配对开关、连接、a2dp连接、hfp连接状态(仅支持带bt蓝牙的设备)事件号
getBtNotice(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_set_bt_notice),

/// 查询bt配对开关、连接、a2dp连接、hfp连接状态(仅支持带bt蓝牙的设备)
libManager.send(evt: CmdEvtType.getBtNotice, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名              | 字段类型 | 字段说明                                                     |
| ------------------- | -------- | ------------------------------------------------------------ |
| bt_connect_states   | int      | 85：bt连接状态开<br />170：bt连接状态关<br />0：无效   |
| bt_pair_states      | int      | 85：bt配对状态开<br />170：bt配对状态关<br />0：无效   |
| a2dp_connect_states | int      | 85：a2dp连接状态开<br />170：a2dp连接状态关<br />0：无效 |
| hfp_connect_states  | int      | 85：hfp连接状态开<br />170：hfp连接状态关<br />0：无效 |


`示例：`

```c
{
    "bt_connect_states":85,
    "bt_pair_states":85,
    "a2dp_connect_states":85,
    "hfp_connect_states":85
}
```
