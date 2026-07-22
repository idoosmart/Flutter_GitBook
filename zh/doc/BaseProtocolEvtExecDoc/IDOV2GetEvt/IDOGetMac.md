### 获取设备mac地址


功能表:每个设备支持 【getBtAddrV2】

**Flutter示例：**

```dart
/// 获取mac地址事件号
getMac(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_app_get_mac),

/// 获取mac地址
libManager.send(evt: CmdEvtType.getMac, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                 |
| -------- | -------- | ------------------------ |
| mac_addr | int [6]  | 设备的id地址 最大6个字节 |
| bt_addr  | int [6]  | bt的蓝牙地址 最大6个字节 |

`示例：`

```c
{
  "bt_addr" :
  [
    135,
    0,
    23,
    0,
    136,
    173
  ],
  "mac_addr" :
  [
    173,
    136,
    0,
    23,
    0,
    135
  ]
}
```
