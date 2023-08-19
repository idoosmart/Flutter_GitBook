### APP传输运动图标信息及状态通知固件


**Flutter示例：**

```dart
/// app传输运动图标信息及状态通知固件事件号
setNoticeIconInformation(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_notcie_icon_informationg
),

/// app传输运动图标信息及状态通知固件
libManager.send(evt: CmdEvtType.setNoticeIconInformation, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名   | 字段类型 | 字段说明                             |
| -------- | -------- | ------------------------------------ |
| states   | int      | 0：开始传输  <br />16：结束传输 |
| icon_num | int      | 图标传输数量                         |

`示例：`

```c
{
    "states":0,
    "icon_num":0
}
```

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明                     |
| ------ | -------- | ---------------------------- |
| status | int      | 成功：0  <br />失败：1 |

`示例：`

```c
{
    "states":1
}
```

