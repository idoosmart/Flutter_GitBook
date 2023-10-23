### 设置环境音量的开关和阀值


功能表：syncV3Noise

**Flutter示例：**

```dart
/// 环境音量的开关和阀值事件号
setV3Noise(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_v3_noise),

/// 环境音量的开关和阀值
libManager.send(evt: CmdEvtType.setV3Noise, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名            | 字段类型 | 字段说明                                |
| ----------------- | -------- | --------------------------------------- |
| mode              | int      | 全天环境音量开关 <br />1:开<br />0:关闭 |
| start_hour        | int      | 开始时间 时                             |
| start_minute      | int      | 开始时间 分                             |
| end_hour          | int      | 结束时间 时                             |
| end_minute        | int      | 结束时间 分                             |
| high_noise_on_off | int      | 阀值开关 <br />1:开<br />0:关闭         |
| high_noise_value  | int      | 阀值                                    |

`示例：`

```c
{
  "mode":1,
    "start_hour":15,
    "start_minute":0,
    "end_hour":20,
    "end_minute":0,
    "high_noise_on_off":1,
    "high_noise_value":100,
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`

```c
{
  "is_success":1
}
```
