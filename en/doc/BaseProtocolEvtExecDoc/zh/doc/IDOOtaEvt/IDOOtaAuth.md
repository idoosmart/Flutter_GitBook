### 设置ota授权


**Flutter示例：**

```dart
/// ota授权事件号
otaAuth(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_ota_auth),

/// ota授权
libManager.send(evt: CmdEvtType.otaAuth, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名    | 字段类型 | 字段说明                                          |
| --------- | -------- | ------------------------------------------------- |
| device_id | int      | 设备ID                                            |
| version   | int      | 版本0 表示不进行版本校验,用于不能降级的约束,默认0 |

`示例：`

```c
{
    "device_id":0,
    "version":0
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| err_code | int      | 错误码<br />0：校验成功<br />1：ID号校验失败<br />2：版本号校验失败<br />3：电量不足<br />4：其他错误 |

`示例：`

```c
{
    "err_code":0
}
```