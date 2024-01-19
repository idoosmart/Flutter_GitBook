### 设置运动模式


**Flutter示例：**

```dart
/// 设置运动模式选择事件号
setSportModeSelect(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_sport_mode_select),

/// 设置运动模式选择
libManager.send(evt: CmdEvtType.setSportModeSelect, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                            | 字段类型 | 字段说明                                                     |
| --------------------------------- | -------- | ------------------------------------------------------------ |
| flag                              | int      | 0：无效<br />1：快捷运动类型设置，下发sport_type1 & sport_type2 & sport_type3 & sport_type4<br />2：快捷运动类型具体运动设置 |
| sport_type1                       | int      | 快捷运动类型1 <br />flag:1有效                            |
| sport_type2                       | int      | 快捷运动类型2 <br />flag:1有效                            |
| sport_type3                       | int      | 快捷运动类型3 <br />flag:1有效                            |
| sport_type4                       | int      | 快捷运动类型4 <br />flag:1有效                            |
| sport_type0_walk                  | bool     | 类型：走路，0不支持，1支持 <br />flag:2有效               |
| sport_type0_run                   | bool     | 类型：跑步，0不支持，1支持 <br />flag:2有效               |
| sport_type0_by_bike               | bool     | 类型：骑行，0不支持，1支持 <br />flag:2有效               |
| sport_type0_on_foot               | bool     | 类型：徒步，0不支持，1支持 <br />flag:2有效               |
| sport_type0_swim                  | bool     | 类型：游泳，0不支持，1支持 <br />flag:2有效               |
| sport_type0_mountain_climbing     | bool     | 类型：爬山，0不支持，1支持 <br />flag:2有效               |
| sport_type0_badminton             | bool     | 类型：羽毛球，0不支持，1支持 <br />flag:2有效             |
| sport_type0_other                 | bool     | 类型：其他，0不支持，1支持 <br />flag:2有效               |
| sport_type1_fitness               | bool     | 类型：健身，0不支持，1支持 <br />flag:2有效               |
| sport_type1_spinning              | bool     | 类型：动感单车，0不支持，1支持 <br />flag:2有效           |
| sport_type1_ellipsoid             | bool     | 类型：椭圆球，0不支持，1支持 <br />flag:2有效             |
| sport_type1_treadmill             | bool     | 类型：跑步机，0不支持，1支持 <br />flag:2有效             |
| sport_type1_sit_up                | bool     | 类型：仰卧起坐，0不支持，1支持 <br />flag:2有效           |
| sport_type1_push_up               | bool     | 类型：俯卧撑，0不支持，1支持 <br />flag:2有效             |
| sport_type1_dumbbell              | bool     | 类型：哑铃，0不支持，1支持 <br />flag:2有效               |
| sport_type1_weightlifting         | bool     | 类型：举重，0不支持，1支持 <br />flag:2有效               |
| sport_type2_bodybuilding_exercise | bool     | 类型：健身操，0不支持，1支持 <br />flag:2有效             |
| sport_type2_yoga                  | bool     | 类型：瑜伽，0不支持，1支持 <br />flag:2有效               |
| sport_type2_rope_skipping         | bool     | 类型：跳绳，0不支持，1支持 <br />flag:2有效               |
| sport_type2_table_tennis          | bool     | 类型：乒乓球，0不支持，1支持 <br />flag:2有效             |
| sport_type2_basketball            | bool     | 类型：篮球，0不支持，1支持 <br />flag:2有效               |
| sport_type2_footballl             | bool     | 类型：足球，0不支持，1支持 <br />flag:2有效               |
| sport_type2_volleyball            | bool     | 类型：排球，0不支持，1支持 <br />flag:2有效               |
| sport_type2_tennis                | bool     | 类型：网球，0不支持，1支持 <br />flag:2有效               |
| sport_type3_golf                  | bool     | 类型：高尔夫，0不支持，1支持 <br />flag:2有效             |
| sport_type3_baseball              | bool     | 类型：棒球，0不支持，1支持 <br />flag:2有效               |
| sport_type3_skiing                | bool     | 类型：滑雪，0不支持，1支持<br /> flag:2有效               |
| sport_type3_roller_skating        | bool     | 类型：轮滑，0不支持，1支持 <br />flag:2有效               |
| sport_type3_dance                 | bool     | 类型：跳舞，0不支持，1支持 <br />flag:2有效               |
| sport_type3_strength_training     | bool     | 类型：力量训练，0不支持，1支持 <br />flag:2有效           |
| sport_type3_core_training         | bool     | 类型：核心训练，0不支持，1支持 <br />flag:2有效           |
| sport_type3_tidy_up_relax         | bool     | 类型：整理放松，0不支持，1支持 <br />flag:2有效           |

`示例：`

```c
{
  "flag":2,
  "sport_type1":0,
  "sport_type2":0,
  "sport_type3":0,
  "sport_type4":0,
  "sport_type0_walk":1,
  "sport_type0_run":1,
  "sport_type0_by_bike":1,
  "sport_type0_on_foot":1,
  "sport_type0_swim":1,
  "sport_type0_mountain_climbing":1,
  "sport_type0_badminton":1,
  "sport_type0_other":1,
  "sport_type1_fitness":1,
  "sport_type1_spinning":1,
  "sport_type1_ellipsoid":1,
  "sport_type1_treadmill":1,
  "sport_type1_sit_up":1,
  "sport_type1_push_up":1,
  "sport_type1_dumbbell":1,
  "sport_type1_weightlifting":1,
  "sport_type2_bodybuilding_exercise":1,
  "sport_type2_yoga":1,
  "sport_type2_rope_skipping":1,
  "sport_type2_table_tennis":1,
  "sport_type2_basketball":1,
  "sport_type2_footballl":1,
  "sport_type2_volleyball":1,
  "sport_type2_tennis":1,
  "sport_type3_golf":1,
  "sport_type3_baseball":1,
  "sport_type3_skiing":1,
  "sport_type3_roller_skating":1,
  "sport_type3_dance":1,
  "sport_type3_strength_training":1,
  "sport_type3_core_training":1,
  "sport_type3_tidy_up_relax":0
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

