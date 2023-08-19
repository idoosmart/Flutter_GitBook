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
| burn_fat_threshold  | int      | 脂肪训练 50%-69%                     |
| aerobic_threshold   | int      | 心肺训练 70%-84%                     |
| limit_threshold     | int      | 峰值训练 85%-100%                    |
| user_max_hr         | int      | 心率上限的意思，最大心率提醒         |
| range1              | int      | 热身运动 98（220 - 年龄） * 50       |
| range2              | int      | 脂肪燃烧  118  （220 - 年龄） * 60   |
| range3              | int      | 有氧运动  138   （220 - 年龄） * 70  |
| range4              | int      | 无氧运动  157  （220 - 年龄） * 80   |
| range5              | int      | 极限锻炼  177   （220 - 年龄） * 90  |
| min_hr              | int      | 心率最小值                           |
| max_hr_remind       | int      | 最大心率提醒<br />0 关闭,1 开启 |
| min_hr_remind       | int      | 最小心率提醒<br />0 关闭,1 开启 |
| remind_start_hour   | int      | 提醒开始 时                          |
| remind_start_minute | int      | 提醒开始 分                          |
| remind_stop_hour    | int      | 提醒结束 时                          |
| remind_stop_minute  | int      | 提醒结束 分                          |

`示例：`

```c
{
  "burn_fat_threshold":50,
  "aerobic_threshold":70,
  "limit_threshold":80,
  "user_max_hr":120,
  "range1":0,
  "range2":0,
  "range3":0,
  "range4":0,
  "range5":0,
  "min_hr":76,
  "max_hr_remind":1,
  "min_hr_remind":1,
  "remind_start_hour":9,
  "remind_start_minute":0,
  "remind_stop_hour":23,
  "remind_stop_minute":0
}
```

