### 获取压力值


功能表:setSetStressCalibration

**Flutter示例：**

```dart
/// 获取压力值事件号
getStressVal(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_stress_val),

/// 获取压力值
libManager.send(evt: CmdEvtType.getStressVal, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明 |
| ---------- | -------- | -------- |
| stress_val | int      | 压力值   |
| threshold  | int      | 阈值     |

`示例：`

```c
{
    "stress_val":0,
    "threshold":0
}
```
