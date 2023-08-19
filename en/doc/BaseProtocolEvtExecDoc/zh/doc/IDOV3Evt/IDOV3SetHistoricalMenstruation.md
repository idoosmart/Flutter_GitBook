### V3经期的历史数据下发


功能表:setHistoryMenstrual

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
| version           | int      | 协议库版本号                                                 |
| avg_menstrual_day | int      | 平均经期长度                                                 |
| avg_cycle_day     | int      | 平均周期长度                                                 |
| items_len         | int      | 增加、修改有效<br />消息通知总开关  170:开启总通知开关， 85:关闭总通知开关 |
| items             | 集合     | 经期历史数据详情<br />year & mon & day & menstrual_day & cycle_day的集合 |

| 字段名        | 字段类型 | 字段说明              |
| ------------- | -------- | --------------------- |
| year          | int      | 经期开始的年          |
| mon           | int      | 经期开始的月          |
| day           | int      | 经期开始的日          |
| menstrual_day | int      | 经期长度 <br />单位天 |
| cycle_day     | int      | 周期长度 <br />单位天 |

`示例：`

```c
{
  "version": 0,
  "avg_menstrual_day": 0,
  "avg_cycle_day": 0,
  "items_len": 2,
  "items": [
    {
        "year": 0,
        "mon": 0,
        "day": 0,
        "menstrual_day": 0,
        "cycle_day":0,
    },
    {
        "year": 0,
        "mon": 0,
        "day": 0,
        "menstrual_day": 0,
        "cycle_day":0,
    }
  ]
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明              |
| -------- | -------- | --------------------- |
| err_code | int      | 错误码 0成功，非0失败 |

`示例：`

```c
{
  "err_code": 0
}
```

