### v2血压校准


功能表：getSupportBpSetOrMeasurementV2

**Flutter示例：**

```dart
/// 血压校准事件号
setBpCalibration(
  evtBase: _VBusEvtBase.base_app_set, 
  evtType: _VBusEvtType.app_set_bp_cal),

/// 血压校准
libManager.send(evt: CmdEvtType.setBpCalibration, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名    | 字段类型 | 字段说明                                |
| --------- | -------- | --------------------------------------- |
| flag      | int      | 1:血压校准设置 <br />2:血压校准查询结果 |
| diastolic | int      | 收缩压                                  |
| systolic  | int      | 舒张压                                  |

`示例：`

```c
{
  "flag":2,
  "diastolic":0,
  "systolic":0
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| ret_code | int      | 0：成功 <br />1：成功进入校准模式，正在校准 <br />2：在运动模式<br />3：设备忙碌<br />4：无效的状态 |

`示例：`

```c
{
  "ret_code":4
}
```

