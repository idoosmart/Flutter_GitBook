### V3多运动数据交互

功能表：syncV3ActivityExchangeData 【syncExchangeDataReplyAddRealTimeSpeedPaceV3，setSupportSportPlan，setSupportExchangeSetGpsCoordinates】


**Flutter示例：**

```dart
/// app发起数据v3交换过程事件号
exchangeAppV3Ing(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_activity_data_exchange),

/// app发起数据v3交换过程
libManager.send(evt: CmdEvtType.exchangeAppV3Ing, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| version         | int      | 协议版本号 默认0 <br />固件开启功能表`syncExchangeDataReplyAddRealTimeSpeedPaceV3`时version=16 <br />固件开启功能表`setSupportSportPlan`时version=32 |
| type            | int      | 运动类型                                                     |
| signal_flag     | int      | 0 ：表示信号弱  <br />1 ：表示信号强                         |
| distance        | int      | app距离<br />单位米<br />app信号强的时候ble使用app的距离数据计算 <br />app信号弱的时候ble不使用app的数据，app显示使用手环的数据 |
| real_time_speed | int      | app计算显示实时配速，预留<br />单位km/h，100倍               |
| duration        | int      | 持续时间 预留<br />单位米                                    |
| calories        | int      | 卡路里  预留<br />单位Kcal                                   |
| gps_info_count  | int      | gps坐标个数，最大支持下发30<br />功能表`setSupportExchangeSetGpsCoordinates`开启时支持 |
| gps             | char []  | gps坐标，最大支持下发30组<br />功能表`setSupportExchangeSetGpsCoordinates`开启时支持 |

`示例：`

```json
{
  "version":0,
  "type":31,
  "signal_flag":0,
  "distance":0,
  "real_time_speed":0,
  "duration":0,
  "calories":0,
  "gps_info_count" : 2,
  "gps" : [
    {
      "latitude" :22543100,
      "longitude" :114057800
    },
    {
      "latitude" :23129100,
      "longitude" :113264400
    }
  ]
}
```

**App收到的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| version              | int      | 协议版本号<br />0：基础版本<br />16：biggerfive定制项目<br />需要固件开启`syncExchangeDataReplyAddRealTimeSpeedPaceV3`<br />32：新增跑步计划数据 需要固件开启功能表`setSupportSportPlan`时version=32 |
| type                 | int      | 运动类型<br />act_type为0有效                                |
| day                  | int      | 数据时间 日                                                  |
| hour                 | int      | 数据时间 时                                                  |
| minute               | int      | 数据时间 分                                                  |
| second               | int      | 数据时间 秒                                                  |
| heart_rate           | int      | 心率数据<br />单位:bpm                                       |
| distance             | int      | 距离 <br />单位根据单位设置的单位显示                        |
| real_time_speed      | int      | 实时速度，单位km/h，扩大100倍                                |
| km_speed             | int      | 实时公里配速 单位s/公里                                      |
| real_time_calories   | int      | 动态卡路里                                                   |
| steps                | int      | 步数                                                         |
| swim_posture         | int      | 主泳姿                                                       |
| status               | int      | 状态 <br />0：无效<br />1：开始<br />2：手动暂停<br />3：结束<br />4：自动暂停 |
| duration             | int      | 持续时间 秒钟数据                                            |
| real_time_speed_pace | int      | 实时的配速 单位秒 <br />5秒使用滑动平均，第5秒使用1-5秒数据，第6秒使用2-6秒数据。第1-4秒不显示配速或速度<br />需要固件开启功能表`syncExchangeDataReplyAddRealTimeSpeedPaceV3`<br />功能表未开启返回0 |
| te                   | int      | 有氧训练效果等级  单位无  范围 0-50 扩大10倍传输<br />需要固件开启功能表`syncExchangeDataReplyAddRealTimeSpeedPaceV3`<br />功能表未开启返回0 |
| tean                 | int      | 无氧运动训练效果等级 单位无  范围 0-50 扩大10倍传输<br />需要固件开启功能表`syncExchangeDataReplyAddRealTimeSpeedPaceV3`<br />功能表未开启返回0 |
| action_type          | int      | 动作类型  <br />1快走<br />2慢跑<br />3中速跑<br />4快跑  <br />5结束课程运动 （还要等待用户是否有自由运动）<br />6课程结束后自由运动（此字段当operate为5起作用）<br />运动累积时间=课程内训练时间+课程结束后计时<br />需要固件开启功能表`setSupportSportPlan` 功能表未开启返回0 |
| count_hour           | int      | action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）<br />action_type = 6时，该字段是课程结束后计时（注：时间递增）<br />需要固件开启功能表`setSupportSportPlan` 功能表未开启返回0 |
| count_minute         | int      | action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）<br />action_type = 6时，该字段是课程结束后计时（注：时间递增）<br />需要固件开启功能表`setSupportSportPlan` 功能表未开启返回0 |
| count_second         | int      | action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）<br />action_type = 6时，该字段是课程结束后计时（注：时间递增）<br />需要固件开启功能表`setSupportSportPlan` 功能表未开启返回0 |

`示例：`

```json
{
    "version":0,
    "type":0,
    "day":0,
    "hour":0,
    "minute":0,
    "second":0,
    "heart_rate":0,
    "distance":0,
    "real_time_speed":0,
    "km_speed":0,
    "real_time_calories":0,
    "steps":0,
    "swim_posture":0,
    "status":0,
    "duration":0,
    "real_time_speed_pace":0,
    "te":0,
    "tean":0,
    "action_type":0,
    "count_hour":0,
    "count_minute":0,
    "count_second":0
}
```