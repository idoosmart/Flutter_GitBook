### 获取全天步数目标


功能表:getStepDataTypeV2

**Flutter示例：**

```dart
/// 获取全天步数目标事件号
getStepGoal(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_step_goal),

/// 获取全天步数目标
libManager.send(evt: CmdEvtType.getStepGoal, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| step      | int      | 全天步数日目标                                               |
| step_week | int      | 全天步数周目标<br />v2_support_set_step_data_type_03_03开启 有效 |

`示例：`

```c
{
    "step":2000,
    "step_week":6000
}
```
