### 设置血压测量


功能表：getSupportBpSetOrMeasurementV2

**Flutter示例：**

```dart
/// 血压测量事件号
setBpMeasurement(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_bp_measure),

/// 血压测量
libManager.send(evt: CmdEvtType.setBpMeasurement, json: jsonEncode(json));
```

**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                                                   |
| ------ | -------- | ---------------------------------------------------------- |
| flag   | int      | 1：开始测量<br />2：结束测量<br />3：获得血压数据 |

`示例：`

```c
{
  "flag":1
}
```



**App收到的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| status       | int      | 0：不支持<br />1：正在测量<br />2：测量成功<br />3：测量失败<br />4：设备正在运动模式 |
| systolic_bp  | int      | 高压/收缩压                                                  |
| diastolic_bp | int      | 低压/舒张压                                                  |

`示例：`

```c
{
  "status":170,
  "systolic_bp":120,
  "diastolic_bp":68
}
```

