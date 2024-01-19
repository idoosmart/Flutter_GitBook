### 设置心率区间


**Flutter示例：**

```dart
/// 设置心率区间事件号
setHeartRateInterval(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_heart_rate_interval),

/// 设置心率区间
libManager.send(evt: CmdEvtType.setHeartRateInterval, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名              | 字段类型 | 字段说明                             |
| ------------------- | -------- | ------------------------------------ |
| burn_fat_threshold  | int      | 脂肪训练心率区间 <br />计算规则:最大心率的50%-69%<br />单位:次/分钟 |
| aerobic_threshold   | int      | 心肺训练心率区间 <br />计算规则:最大心率的70%-84%<br />单位:次/分钟 |
| limit_threshold     | int      | 峰值训练心率区间 <br />计算规则:最大心率的85%-100%<br />单位:次/分钟 |
| user_max_hr         | int      | 心率上限,最大心率提醒<br />单位:次/分钟 |
| range1              | int      | 热身运动心率区间<br />计算规则：(200-年龄) * 50<br />单位:次/分钟 |
| range2              | int      | 脂肪燃烧心率区间<br />计算规则：(200-年龄) * 60<br />单位:次/分钟 |
| range3              | int      | 有氧运动心率区间<br />计算规则：(200-年龄) * 70<br />单位:次/分钟 |
| range4              | int      | 无氧运动心率区间<br />计算规则：(200-年龄) * 80<br />单位:次/分钟 |
| range5              | int      | 极限锻炼心率区间<br />计算规则：(200-年龄) * 90<br />单位:次/分钟 |
| min_hr              | int      | 心率最小值<br />单位:次/分钟            |
| max_hr_remind       | int      | 最大心率提醒<br />0 关闭,1 开启 |
| min_hr_remind       | int      | 最小心率提醒<br />0 关闭,1 开启 |
| remind_start_hour   | int      | 提醒开始 时                          |
| remind_start_minute | int      | 提醒开始 分                          |
| remind_stop_hour    | int      | 提醒结束 时                          |
| remind_stop_minute  | int      | 提醒结束 分                          |

`示例：`

```c
{
  "burn_fat_threshold":113,
  "aerobic_threshold":132,
  "limit_threshold":170,
  "user_max_hr":220,
  "range1":94,
  "range2":113,
  "range3":132,
  "range4":151,
  "range5":170,
  "min_hr":20,
  "max_hr_remind":1,
  "min_hr_remind":0,
  "remind_start_hour":0,
  "remind_start_minute":0,
  "remind_stop_hour":23,
  "remind_stop_minute":59
}
```

