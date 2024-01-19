### 获取SN信息


功能表:supportGetSnInfo

**Flutter示例：**

```dart
/// 获取sn事件号
getSnInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_sn_info)

/// 获取sn
libManager.send(evt: CmdEvtType.getSnInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明                        |
| ------ | -------- | ------------------------------- |
| len    | int      | sn字符串长度                    |
| sn     | char []  | sn序列号字符串,最大长度17个字节 |

`示例：`

```json
{
  "len":11,
  "sn":"as1d65sa2qs"
}
```

