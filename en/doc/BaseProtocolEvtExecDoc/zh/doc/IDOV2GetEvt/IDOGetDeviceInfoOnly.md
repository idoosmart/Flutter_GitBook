### 获取设备信息(不包含bt名称,初次绑定时获取设备信息调用该接口)


功能表:每个设备支持

**Flutter示例：**

```dart
/// 获取设备信息(绑定前专用)事件号
getDeviceInfoOnly(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.intapp_get_device_info_only),

/// 获取设备信息(绑定前专用)
libManager.send(evt: CmdEvtType.getDeviceInfoOnly, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                         | 字段类型 | 字段说明                                                     |
| ------------------------------ | -------- | ------------------------------------------------------------ |
| deivce_id                      | int      | 设备id                                                       |
| firmware_version               | int      | 版本号                                                       |
| mode                           | int      | 模式<br />0：运动模式，<br />1：睡眠模式               |
| batt_status                    | int      | 电池状态 <br />0： 正常<br />1：正在充电<br />2：充满<br />3：低电量 |
| energe                         | int      | 电量等级                                                     |
| pair_flag                      | int      | 绑定状态                                                     |
| reboot                         | int      | 是否重启 <br />如果重启 app会再次同步配置信息给手环          |
| bind_confirm_method            | int      | 绑定确认方式 <br />0：默认(注意以前ID号定制),超时时间无效<br />1：单击[按键在下面]<br />2：为长按[按键在下面]<br />3：屏幕点击 横向确认和取消,确认在左边<br />4：屏幕点击 横向确认和取消,确认在右边<br />5：屏幕点击 竖向确认和取消，确认在上边<br />6：屏幕点击 竖向确认和取消，确认在下边<br />7：点击(右边一个按键) |
| bind_confirm_timeout           | int      | 超时时间<br />最长为15秒 0表示不超时                         |
| platform                       | int      | 手环的平台 <br />0   ：nordic<br />10 ：realtek 8762x <br />20 ：cypress psoc6<br />30：Apollo3 <br />40：为汇顶  <br />50：nordic+泰凌微, 瑞坤 <br />80：5340   <br />90：炬芯 |
| shape                          | int      | 0：默认（gt01 方形的）<br />1：圆形<br />2：方形的<br />3：椭圆 |
| dev_type                       | int      | 0：默认（gt01 手表）<br />1： 手环<br />2：手表              |
| user_defined_dial_main_version | int      | 自定义表盘主版本 从1开始  <br />0：不支持对应的自定义表盘功能 |
| cloud_clock_dial_version       | int      | 云端表盘版本号 默认从0开始 <br />是否支持云端表盘有对应的功能表multi_dial (废弃 同user_defined_dial_main_version ) |
| show_bind_choice_ui            | int      | 固件绑定时候显示勾勾叉叉ui界面  app根据这个位显示提示固件点击绑定  <br />0：不需要app提示  1：需要app提示 |
| bootload_version               | int      | nordic平台bootloader版本信息  最小为1                        |

`示例：`

```c
{
  "batt_status" : 0,
  "bind_confirm_method" : 0,
  "bind_confirm_timeout" : 0,
  "bootload_version" : 0,
  "cloud_clock_dial_version" : 2,
  "deivce_id" : 7453,
  "dev_type" : 2,
  "energe" : 32,
  "firmware_version" : 2,
  "mode" : 1,
  "pair_flag" : 1,
  "platform" : 30,
  "reboot" : 0,
  "shape" : 2,
  "show_bind_choice_ui" : 0,
  "user_defined_dial_main_version" : 2
}
```
