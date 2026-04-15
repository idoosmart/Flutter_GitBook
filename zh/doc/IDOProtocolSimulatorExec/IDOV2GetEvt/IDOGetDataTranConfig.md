### 获取图标文件传输配置传输 / 获取图片文件传输配置

#### 事件号：334

#### APP端发送：

`发送json字段：`

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| type       | int      | 运动类型 对应的图标类型 <br />0：这个字段无效<br />1：运动小图标<br />2：运动大图标<br />3：运动动画  <br />4：运动等大小图标 <br />5：运动最小图标 |
| evt_type   | int      | 事件类型<br />0是这个字段无效 <br />比如  1：短信,2：邮件，3：微信 .... |
| sport_type | int      | 运动类型<br /> 0是这个字段无效 运动模式类型<br />1 走路,2 跑步.... |

`交互结构体内容：`

```c
struct protocol_data_tran_configure_get
{
    struct protocol_head head;//0x2,0xe9
    uint8_t type;       //运动类型 对应的图标类型 0这个字段无效 1运动小图标 2:运动大图标 3:运动动画 4:运动中等大小图标
 	  uint16_t evt_type;  //事件类型 0是这个字段无效 比如0x01短信 0x02邮件 0x03微信 ...(上限值：0x4E20)
   	uint16_t sport_type;//运动类型 0是这个字段无效 运动模式类型0x01走路 0x02跑步 ...
};
```

`获取图标文件传输配置传输json示例：`

```json
{
  "type" : 1,
  "evt_type" : 1,
  "sport_type" : 1
}
```

`获取图标文件传输配置传输字节数据：`

```c
[0x2,0xe9,0x1,0x1,0x0,0x1,0x0]
```



#### 设备/模拟器发送：

`发送json字段：`

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

`交互结构体内容：`

```c
struct protocol_data_tran_configure_get_reply
{
    struct protocol_head head;
    uint8_t err_code;      //错误码 0是正常，非0是错误
    uint8_t type;   	     //运动类型 对应的图标类型 0这个字段无效 1运动小图标 2运动大图标 3运动动画  4运动中等大小图标
    uint16_t evt_type;     //事件类型 0是这个字段无效 通消息通知 比如 0x01短信 0x02邮件 0x03微信（上限值：0x4E20）
    uint16_t sport_type;   //运动类型 0是这个字段无效 运动模式类型 0x01走路 0x02跑步 
    uint16_t icon_width;   //固件图标需要的宽度和高度（根据type 和 evt_type/sport_type 确定）
    uint16_t icon_height; 
    uint8_t format; 		 	                  //颜色格式
    uint16_t block_size;                    //压缩块大小
    uint8_t big_sports_num;                 //运动图标大图标个数
    uint8_t msg_num; 			                  //消息图标的个数
    uint8_t small_sports_and_animation_num; //运动动画和小图标的个数
    
  	// -------- 20220707 新增运动最小图标、中等图标个数返回 --------
    uint8_t min_samll_num;//运动最小图标个数
    uint8_t medium_num;		//运动中等图标个数
};
```

`回复获取图标文件传输配置传输json示例：`

```json
{
	"err_code": 0,
	"type": 1,
	"evt_type": 1,
	"sport_type": 1,
	"icon_width": 50,
	"icon_height": 50,
	"format": 133,
	"block_size": 1024,
	"big_sports_num": 5,
	"msg_num": 0,
	"small_sports_and_animation_num": 0,
	"medium_num": 0,
  "min_samll_num": 0
}
```

`回复获取图标文件传输配置传输字节数据：`

```c
[0x2,0xe9,0x0,0x1,0x1,0x0,0x1,0x0,0x32,0x0,0x32,0x0,0x85,0x0,0x4,0x5,0x0,0x0,0x0,0x0]
```

