### 获取GPS状态


功能表:getSupportUpdateGps

**Flutter示例：**

```dart
/// 获取gps状态事件号
getGpsStatus(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_gps_status),

/// 获取gps状态
libManager.send(evt: CmdEvtType.getGpsStatus, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| gps_run_status | int      | GPS 运行状态 <br />0 没有运行<br />1 正在搜星<br />2 为正在跟踪 |
| agps_is_valid  | int      | agps 是否有效  有效期剩余小时<br />非0为有效                 |

`示例：`

```c
{
  	"gps_run_status":0,
    "agps_is_valid":0
}
```
