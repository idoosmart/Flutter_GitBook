### 设置压力校准


功能表：setSetStressCalibration

**Flutter示例：**

```dart
/// 设置压力校准事件号
setStressCalibration(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_stress_cal),

/// 设置压力校准
libManager.send(evt: CmdEvtType.setStressCalibration, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                              |
| ------------ | -------- | ------------------------------------- |
| stress_score | int      | 压力分数，1～10                       |
| status       | int      | 0：开始校准设置 <br />1：取消校准设置 |

`示例：`

```c
{
  "stress_score":6,
  "status":0
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| ret_code | int      | 0：成功<br />1：失败-正在校准<br />2：失败-正在充电<br />3：失败-未佩戴<br />4：失败-运动场景中 |

`示例：`

```c
{
  "ret_code":3,
}
```