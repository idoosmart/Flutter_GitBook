### 设置勿扰模式

#### 事件号：116

#### **APP端发送**：

`发送json字段：`

| 字段名                     | 字段类型 | 字段说明                                                     |
| -------------------------- | -------- | ------------------------------------------------------------ |
| switch_flag                | int      | 开关<br />1 开启<br />0 关闭                                 |
| start_hour                 | int      | 开始时间<br />时                                             |
| start_minute               | int      | 开始时间<br />分                                             |
| end_hour                   | int      | 结束时间<br />时                                             |
| end_minute                 | int      | 结束时间<br />分                                             |
| have_time_range            | int      | 是否有时间范围 <br />0 无效<br />1 表示无时间范围<br />2 表示有时间范围<br />功能表`disturbHaveRangRepeat`开启有效 |
| week_repeat                | int      | 预留                                                         |
| noontime_rest_on_off       | int      | 白天勿扰开关 <br />1 开启<br />0 关闭                        |
| noontime_rest_start_hour   | int      | 开始时间<br />时                                             |
| noontime_rest_start_minute | int      | 开始时间<br />分                                             |
| noontime_rest_end_hour     | int      | 结束时间<br />时                                             |
| noontime_rest_end_minute   | int      | 结束时间<br />分                                             |
| all_day_on_off             | int      | 全天勿扰 <br />1 开启<br />0 关闭<br />功能表`setOnlyNoDisturbAllDayOnOff`开启有效 |
| intelligent_on_off         | int      | 智能勿扰开关 <br />1 开启<br />0 关闭<br />功能表`setOnlyNoDisturbSmartOnOff`开启有效 |

`交互结构体内容：`

```c
//防打扰
struct protocol_do_not_disturb
{
  struct protocol_head head;
  uint8_t switch_flag;    //0xAA 开启,0x55 关闭 勿擾1开关 晚上勿扰
  uint8_t start_hour;
  uint8_t start_minute;
  uint8_t end_hour;
  uint8_t end_minute;

  uint8_t have_time_range;    //是否有时间范围 新增字段,功能表,0x00 无效,0x01 表示无时间范围,0x02 表示有时间范围
  uint8_t week_repeat;        //预留

  uint8_t noontime_rest_on_off;//勿擾2开关  白天勿扰
  uint8_t noontime_rest_start_hour; //提醒开始时间
  uint8_t noontime_rest_start_minute;
  uint8_t noontime_rest_end_hour;   //提醒结束时间
  uint8_t noontime_rest_end_minute;
  //bool v2_support_disturb_three_on_off_03_29;//idw05新增：勿扰模式设置获取新增全天勿扰开关
  //注：之前的全天勿扰开关与智能勿扰开关使用的同一个功能表v2_support_disturb_three_on_off_03_29支持,后续为了方便开发,新固件不需要开启前者,转用以下两个功能表去支持 2022-11-7
  //bool support_v2_disturb_all_day_switch_03_29; //支持设置全天勿扰开关
  //bool support_v2_disturb_smart_switch_03_29; //支持设置智能勿扰开关
  uint8_t all_day_on_off;//20220627新增 全天勿扰开关   
  uint8_t intelligent_on_off; //20220627新增 智能勿扰开关  
};
```

`设置勿扰模式json示例：`

```json
{
	"switch_flag": 1,
	"start_hour": 15,
	"start_minute": 23,
	"end_hour": 23,
	"end_minute": 30,
	"have_time_range": 2,
	"week_repeat": 127,
	"noontime_rest_on_off": 1,
	"noontime_rest_start_hour": 9,
	"noontime_rest_start_minute": 0,
	"noontime_rest_end_hour": 12,
	"noontime_rest_end_minute": 0,
	"all_day_on_off": 0,
	"intelligent_on_off": 0
}
```

`设置勿扰模式字节数据：`

```c
[0x03,0x29,0x1,0xf,0x17,0x17,0x1e,0x2,0x7f,0x1,0x9,0x0,0xc,0x0,0x0,0x0]
```



#### **设备/模拟器发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd; //0x3
  uint8_t key; //0x29
};
```

`回复设置勿扰模式json示例：`

无

`回复设置勿扰模式字节数据：`

```c
[0x03,0x29]
```

