### 获取错误记录


功能表:getFlashLog

**Flutter示例：**

```dart
/// 获取错误记录事件号
getErrorRecord(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_error_record),

/// 获取错误记录
libManager.send(evt: CmdEvtType.getErrorRecord, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                     |
| ------ | -------- | ---------------------------- |
| type   | int      | 0 查询<br />1 清除记录 |

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| type       | int      | 0 查询<br />1 清除记录                                 |
| reset_flag | int      | 0 正常<br />1 硬错误(Hard Faul)<br />2 看门狗服务<br />3 断言复位<br />4 掉电服务<br />5 其他异常 |
| hw_error   | int      | 硬件错误码 <br />0 正常<br />1 加速度错误<br />2 心率错误<br />3 TP错误<br />4 flash错误 |

`示例：`

```c
{
  "type":0,
  "reset_flag":0,
  "hw_error":0
}
```
