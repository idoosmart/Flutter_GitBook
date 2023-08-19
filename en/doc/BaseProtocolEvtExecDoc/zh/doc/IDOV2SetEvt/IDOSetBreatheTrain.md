### 设置呼吸训练


功能表：setSupportBreathRate

**Flutter示例：**

```dart
/// 呼吸训练事件号
setBreatheTrain(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_breathe_train),

/// 呼吸训练
libManager.send(evt: CmdEvtType.setBreatheTrain, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名    | 字段类型 | 字段说明       |
| --------- | -------- | -------------- |
| frequency | int      | 每分钟呼吸次数 |

`示例：`

```c
{
   "frequency":30
}
```

