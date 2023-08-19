### 获取运动模式自动识别开关


功能表:getActivitySwitch

**Flutter示例：**

```dart
/// 运动模式自动识别开关获取事件号
getActivitySwitch(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_activity_switch),

/// 运动模式自动识别开关获取
libManager.send(evt: CmdEvtType.getActivitySwitch, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                         | 字段类型 | 字段说明                            |
| ------------------------------ | -------- | ----------------------------------- |
| err_code                       | int      | 0是成功<br />非0 是错误             |
| auto_identify_sport_walk       | int      | 自动识别走路开关 0 关闭,1 开   |
| auto_identify_sport_run        | int      | 自动识别跑步开关 0 关闭,1 开   |
| auto_identify_sport_bicycle    | int      | 自动识别自行车开关 0 关闭,1 开 |
| auto_pause_on_off              | int      | 运动自动暂停 0 关闭,1 开       |
| auto_end_remind_on_off_on_off  | int      | 结束提醒 0 关闭,1 开           |
| auto_identify_sport_elliptical | int      | 自动识别椭圆机开关 0 关闭,1 开 |
| auto_identify_sport_rowing     | int      | 自动识别划船机开关 0 关闭,1 开 |
| auto_identify_sport_swim       | Int      | 自动识别游泳开关 0 关闭,1 开   |

`示例：`

```c
{
    "err_code":0,
    "auto_identify_sport_walk":0,
    "auto_identify_sport_run":0,
    "auto_identify_sport_bicycle":0,
    "auto_pause_on_off":0,
    "auto_end_remind_on_off_on_off":0,
    "auto_identify_sport_elliptical":0,
    "auto_identify_sport_rowing":0,
    "auto_identify_sport_swim":0
}
```

