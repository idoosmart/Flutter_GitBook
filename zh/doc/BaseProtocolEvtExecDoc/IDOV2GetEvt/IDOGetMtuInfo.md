### 获取mtu信息


功能表:getMtu

**Flutter示例：**

```dart
/// 获取mtu信息事件号
getMtuInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_mtu_info),

/// 获取mtu信息
libManager.send(evt: CmdEvtType.getMtuInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| status     | int      | 0 表示数据有效<br />1 表示数据无效,等一会儿再获取,数据无效的情况下,mtu 都是20 |
| rx_mtu     | int      | app接收mtu                                                   |
| tx_mtu     | int      | app发送mtu                                                   |
| phy_speed  | int      | 物理层速度<br />0 为无效<br />1000 为1M<br />2000 为2M<br />512为512K |
| dle_length | int      | DLE长度<br />0表示不支持                                     |

`示例：`

```c
{
  "dle_length" : 27,
  "phy_speed" : 285,
  "rx_mtu" : 132,
  "status" : 0,
  "tx_mtu" : 132
 }
```

