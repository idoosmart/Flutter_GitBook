### 设置运动模式识别开关


功能表：setActivitySwitch【getAutoActivitySetGetUseNewStructExchange】

**Flutter示例：**

```dart
/// 运动开关设置事件号
setActivitySwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_activity_switch),

/// 运动开关设置
libManager.send(evt: CmdEvtType.setActivitySwitch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                         | 字段类型 | 字段说明                            |
| ------------------------------ | -------- | ----------------------------------- |
| auto_identify_sport_walk       | int      | 自动识别走路开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_run        | int      | 自动识别跑步开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_bicycle    | int      | 自动识别自行车开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_pause_on_off              | int      | 运动自动暂停 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_end_remind_on_off_on_off  | int      | 结束提醒 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_elliptical | int      | 自动识别椭圆机开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_rowing     | int      | 自动识别划船机开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_swim       | int      | 自动识别游泳开关 <br />0 关闭<br />1 开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |
| auto_identify_sport_smart_rope | int | 自动识别智能跳绳开关 <br />0关闭<br />1开<br />功能表`getAutoActivitySetGetUseNewStructExchange`开启后，通过获取识别开关`libManager.send(evt: CmdEvtType.setActivitySwitch)`判断此开关支不支持(-1 不支持) |

`示例：`

```c
{
   "auto_identify_sport_walk":1,
   "auto_identify_sport_run":0,
   "auto_identify_sport_bicycle":0,
   "auto_pause_on_off":0,
   "auto_end_remind_on_off_on_off":1,
   "auto_identify_sport_elliptical":0,
   "auto_identify_sport_rowing":0,
   "auto_identify_sport_swim":0,
   "auto_identify_sport_smart_rope":0
}
```
