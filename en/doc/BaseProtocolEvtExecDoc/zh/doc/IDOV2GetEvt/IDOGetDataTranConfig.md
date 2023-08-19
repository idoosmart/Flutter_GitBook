### 获取图标文件传输配置传输 / 获取图片文件传输配置


功能表:getNotifyIconAdaptive

**Flutter示例：**

```dart
/// 文件传输配置传输获取事件号
getDataTranConfig(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_data_tran_configure),

/// 文件传输配置传输获取
libManager.send(evt: CmdEvtType.getDataTranConfig, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| type       | int      | 运动类型 对应的图标类型 <br />0：这个字段无效<br />1：运动小图标<br />2：运动大图标<br />3：运动动画  <br />4：运动等大小图标 <br />5：运动最小图标 |
| evt_type   | int      | 事件类型<br />0是这个字段无效 <br />比如  1：短信,2：邮件，3：微信 .... |
| sport_type | int      | 运动类型<br /> 0是这个字段无效 运动模式类型<br />1 走路,2 跑步.... |

`示例：`

```c
{
  "type":1,
  "evt_type":1,
  "sport_type":1
}
```

**App收到的json字段**：

| 字段名                         | 字段类型 | 字段说明                                                     |
| ------------------------------ | -------- | ------------------------------------------------------------ |
| err_code                       | int      | 错误码 0是正常，非0是错误                                    |
| type                           | int      | 运动类型 对应的图标类型 <br />0：这个字段无效<br />1：运动小图标<br />2：运动大图标  <br />3：运动动画  <br />4：运动中等大小图标 |
| evt_type                       | int      | 事件类型<br />0是这个字段无效 <br />比如  1：短信,2：邮件，3：微信 .... |
| sport_type                     | int      | 运动类型<br />0是这个字段无效 运动模式类型, 1 走路,2 跑步.... |
| icon_width                     | int      | 固件图标需要的宽度（根据type 和 evt_type/sport_type 确定）   |
| icon_height                    | int      | 固件图标需要的高度（根据type 和 evt_type/sport_type 确定）   |
| format                         | int      | 颜色格式                                                     |
| block_size                     | int      | 压缩块大小                                                   |
| big_sports_num                 | int      | 运动图标大图标个数                                           |
| msg_num                        | int      | 消息图标的个数                                               |
| small_sports_and_animation_num | int      | 运动动画和小图标的个数                                       |
| medium_num                     | int      | 运动中等图标个数                                             |

`示例：`

```c
{
  	"err_code":0,
    "type":1,
    "evt_type":1,
    "sport_type":1,
    "icon_width":50,
    "icon_height":50,
    "format":133,
    "block_size":1024,
    "big_sports_num":5,
    "msg_num":0,
    "small_sports_and_animation_num":0,
    "medium_num":0
}
```

