### V3经期的历史数据下发


功能表:setHistoryMenstrual 【supportSetHistoricalMenstruationUseVersion2】

**Flutter示例：**

```dart
/// 经期的历史数据下发事件号
getHistoricalMenstruation(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_historical_menstruation),

/// 经期的历史数据下发
libManager.send(evt: CmdEvtType.getHistoricalMenstruation, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| version           | int      | 协议库版本号<br />默认0                                      |
| avg_menstrual_day | int      | 平均经期长度<br />单位天                                     |
| avg_cycle_day     | int      | 平均周期长度<br />单位天                                     |
| items_len         | int      | 经期历史数据详情`items`个数，最大5                           |
| items             | 集合     | 经期历史数据详情<br />`year` & `mon` & `day & menstrual_day` & `cycle_day`的集合<br />`ovulation_interval_day` & `ovulation_before_day` & `ovulation_after_day`在功能表`supportSetHistoricalMenstruationUseVersion2`开启时有效 |

| 字段名                 | 字段类型 | 字段说明                                                     |
| ---------------------- | -------- | ------------------------------------------------------------ |
| year                   | int      | 经期开始的年                                                 |
| mon                    | int      | 经期开始的月                                                 |
| day                    | int      | 经期开始的日                                                 |
| menstrual_day          | int      | 经期长度 <br />单位天                                        |
| cycle_day              | int      | 周期长度 <br />单位天                                        |
| ovulation_interval_day | int      | 从下一个经期开始前到排卵日的间隔,一般为14天<br />功能表`supportSetHistoricalMenstruationUseVersion2`开启有效 |
| ovulation_before_day   | int      | 排卵日之前易孕期的天数,一般为5<br />功能表`supportSetHistoricalMenstruationUseVersion2`开启有效 |
| ovulation_after_day    | int      | 排卵日之后易孕期的天数,一般为5<br />功能表`supportSetHistoricalMenstruationUseVersion2`开启有效 |

`示例：`

```json
{
  "version": 2,
  "avg_menstrual_day": 7,
  "avg_cycle_day": 29,
  "items_len": 1,
  "items": [
    {
      "year": 2023,
      "mon": 8,
      "day": 1,
      "menstrual_day": 7,
      "cycle_day":30,
      "ovulation_interval_day":14,
      "ovulation_before_day":5,
      "ovulation_after_day":5,
    },
    {
      "year": 2023,
      "mon": 8,
      "day": 31,
      "menstrual_day": 7,
      "cycle_day":28,
      "ovulation_interval_day":14,
      "ovulation_before_day":5,
      "ovulation_after_day":5,
    }
  ]
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明              |
| -------- | -------- | --------------------- |
| err_code | int      | 错误码 0成功，非0失败 |

`示例：`

```json
{
  "err_code": 0
}
```

