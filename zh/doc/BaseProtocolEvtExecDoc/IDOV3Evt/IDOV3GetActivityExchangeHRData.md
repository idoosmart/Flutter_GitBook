### V3多运动数据数据交换中获取1分钟的心率数据


**Flutter示例：**

```dart
/// app获取v3心率数据事件号
exchangeAppGetV3HrData(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_activity_exchange_heart_rate_data),

/// app获取v3心率数据
libManager.send(evt: CmdEvtType.exchangeAppGetV3HrData, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                 | 字段类型 | 字段说明                                       |
| ---------------------- | -------- | ---------------------------------------------- |
| version                | int      | 协议版本号<br />预留                           |
| hour                   | int      | 时                                             |
| minute                 | int      | 分                                             |
| second                 | int      | 秒                                             |
| heart_rate_history_len | int      | 心率数据数组长度<br />最大60                   |
| interval_second        | Int      | 心率间隔<br />单位秒                           |
| heart_rate_history     | int []    | 心率数据数组<br />存一分钟的心率数据, 1s存一个 |

`示例：`

```c
{
    "version":0,
    "hour":0,
    "minute":0,
    "second":0,
    "heart_rate_history_len":0,
    "interval_second":0,
    "heart_rate_history":[
        85,
        85,
        86,
        90,
        100,
        80,
        75
    ]
}
```