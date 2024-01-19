### APP设置ALEXA开关命令


功能表:alexaSetSetOnOffTypeV3

**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| type   | int      | 类型<br />0:sport/exercise(跳到运动列表)<br />1:Outdoor Run（户外跑步）<br />2:Indoor run（室内跑步）<br />3:Outdoor walk（户外步行）<br />4:Indoor walk（室内步行）<br />5:Hiking（徒步）<br />6:Outdoor cycle（户外骑行）<br />7:Indoor cycle（室内骑行）<br />8:Cricket（板球）<br />9:Pool Swim（泳池游泳）<br />10:Open water swim（开放式游泳）<br />11:Yoga（瑜伽）<br />12:Rower（划船机）<br />13:Elliptical（椭圆机）<br />14:workout（健身 ）<br />15:sleep/slept(睡眠页面) <br />16:stress/pressure(压力检测) <br />17:help(打开帮助二维码界面)<br />18:find phone (查找手机)<br />19:breath training/relax（呼吸页面）<br />20:settings/Options（设置）<br />21:flashlight（手电筒）<br />22:display  setting/brightness（亮度设置）<br />23:message/text  notifications(消息详情)<br />24:skin temperature(皮肤温度) <br />25:noise measurement(噪音测量) <br />26:phone(打开电话) <br />27:event reminder(事项提醒) <br />28:stopwatch(秒表) <br />29:running course(跑步课程) <br />30:body power(查询身体电量) |
| on_off | int      | 开关<br />170:开<br />85:关                                  |

`示例：`

```c
{
    "total_time":30
}
```

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明         |
| ---------- | -------- | ---------------- |
| is_success | int      | 1：成功 ， 0失败 |

`示例：`

```c
{
    "is_success":1
}
```
