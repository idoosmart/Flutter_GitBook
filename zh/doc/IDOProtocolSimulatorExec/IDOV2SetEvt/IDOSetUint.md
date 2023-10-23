### 设置单位



功能表：【setSupportFahrenheit，setSupportCalorieUnit，setSupportSwimPoolUnit，setSupportCyclingUnit，setSupportWalkRunUnit】

**Flutter示例：**

```dart
/// 设置单位事件号
setUnit(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_unit),

/// 设置单位
libManager.send(evt: CmdEvtType.setUnit, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| dist_unit            | int      | 距离单位<br />0：无效<br />1：km(公制)<br />2：mi（英制） |
| weight_unit          | int      | 体重单位<br />0：无效<br />1：kg<br />2：lb         |
| temp                 | int      | 温度单位<br />0：无效<br/>1：℃<br />2：℉            |
| stride               | int      | 走路步长<br />0：无效<br />0：cm                       |
| language             | int      | 语言                                                         |
| is_12hour_format     | int      | 时间制式<br />0：无效<br/>1：24小时制<br />2：12小时制 |
| stride_run           | int      | 跑步的步长<br />0：无效<br />1：cm<br />根据男性换算,默认值:90cm |
| stride_gps_cal       | int      | 通过手机GPS校准步长开关<br/>0：无效<br />1：开<br />2：关 |
| week_start_date      | int      | 周起始日 <br />0：星期1<br />1：星期天<br />3：星期6 |
| calorie_unit         | int      | 卡路里单位设置<br />0：无效<br />1：默认千卡<br />2：大卡<br />3：千焦 |
| swim_pool_unit       | int      | 泳池单位设置<br />0：无效<br />1：默认米<br />2：码          |
| cycling_unit         | int      | 骑行单位<br />0：无效<br />1：km 公里<br />2：英里           |
| walking_running_unit | int      | 步行或者跑步的单位（公里/英里）设置  <br />0：无效 <br />1：km 公里<br />2：英里<br />需要功能表支持V3_support_walking_running_unit |

`示例：`

```c
{
  "dist_unit":1,
  "weight_unit":1,
  "temp":1,
  "stride":1,
  "language":1,
  "is_12hour_format":1,
  "stride_run":1,
  "stride_gps_cal":1,
  "week_start_date":1,
  "calorie_unit":1,
  "swim_pool_unit":1,
  "cycling_unit":1,
  "walking_running_unit":1
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

