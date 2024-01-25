### 设置运动目标

#### 事件号：105

#### **APP端发送**：

`发送json字段：`

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| sport_step      | int      | 步数                                                         |
| walk_goal_steps | int      | 每小时步数目标设置                                           |
| target_type     | int      | 0无效 <br />1日目标 <br />2周目标 <br />功能表`v2SupportSetStepDataType`开启有效 |

`交互结构体内容：`

```c
//设置目标
struct protocol_set_sport_goal
{
    struct protocol_head head;
    uint8_t type; 			 //00步数 
    uint32_t data;  	   //数值
    uint8_t sleep_hour;  //预留
    uint8_t sleep_minute;//预留

    uint16_t walk_goal_steps; //每小时步数目标设置 功能表 bool support_walk_goal_steps_03_03 //固件支持每小时目标步数设置和获取
  
 		uint8_t target_type;//0无效 1日目标 2周目标 功能表 bool v2_support_set_step_data_type_03_03//支持app设置目标步数类型为周目标
};
```

`设置运动目标示例：`

```json
{
	"sport_step": 2000,
	"walk_goal_steps": 15,
  "target_type" : 1
}
```

`设置运动目标字节数据：`

```c
[0x3,0x3,0x0,0xd0,0x7,0x0,0x0,0x0,0x0,0xf,0x0,0x1]
```



#### **设备/模拟器发送**：

`发送json字段：`

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`交互结构体内容：`

```c
struct protocol_reply
{
  struct protocol_head head;//0x03,0x03
  uint8_t status_code;
};
```

`回复APP设置运动目标的示例：`

```json
{
   "status_code" : 0
}
```

`回复APP设置运动目标字节数据：`

```c
[0x3,0x3,0x0]
```

