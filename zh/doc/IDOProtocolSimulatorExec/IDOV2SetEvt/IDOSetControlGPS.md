### 设置控制gps


**Flutter示例：**

```dart
/// 设置控制GPS事件号
setGpsControl(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_control_gps),

/// 设置控制GPS
libManager.send(evt: CmdEvtType.setGpsControl, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名  | 字段类型 | 字段说明                                                     |
| ------- | -------- | ------------------------------------------------------------ |
| operate | int      | 1：控制 <br />2：查询                                  |
| type    | int      | 1：开启log<br />2：关闭log<br />3：agps写入<br />4：agps 擦除<br />5：gps_fw 写入 |

`示例：`

```c
{
  "operate":2,
  "type":0
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| type       | int      | 1：开启log<br />2：关闭log<br />3：agps写入<br />4：agps 擦除<br />5：gps_fw 写入 |
| status     | int      | 0：为无效<br />1：命令正在执行<br />2：完成                  |
| error_code | int      | 成功：0  <br />非0失败                                    |

`示例：`

```c
{
  "type":2,
  "status":0,
  "error_code":0
}
```
