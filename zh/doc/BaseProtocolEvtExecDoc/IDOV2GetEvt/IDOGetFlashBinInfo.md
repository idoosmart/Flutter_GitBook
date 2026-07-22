### 获取字库信息


功能表:getFlashLog

**Flutter示例：**

```dart
/// 获取字库信息事件号
getFlashBinInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_flash_bin_info),

/// 获取字库信息
libManager.send(evt: CmdEvtType.getFlashBinInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                             |
| ------------- | -------- | ---------------------------------------------------- |
| status        | int      | 状态 0正常,1 字库无效 校验错误,2 版本不匹配 |
| version       | int      | 版本号                                               |
| match_version | int      | 匹配版本号,就是固件需要的字库版本号                  |
| check_code    | int      | 字库校验码                                           |

`示例：`

```c
{
  "check_code" : 1211171869,
  "match_version" : 13,
  "status" : 0,
  "version" : 13
}
```

