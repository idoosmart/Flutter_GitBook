### 进入升级模式


**Flutter示例：**

```dart
/// 进入升级模式事件号
otaStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_ota_start),

/// 进入升级模式
libManager.send(evt: CmdEvtType.otaStart, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| err_flag | int      | 0: 进入OTA成功 <br />1: 失败：电量过低 <br />2: 失败：设备不支持  <br>3: 失败：参数不正确 |

`示例：`

```c
{
    "err_flag":0
}
```

