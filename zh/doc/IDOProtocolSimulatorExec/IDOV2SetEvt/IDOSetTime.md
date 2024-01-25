### 设置时间

#### 事件号：104

#### **APP端发送**：

`发送json字段：`

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| year      | int      | 年                                                           |
| monuth    | int      | 月                                                           |
| day       | int      | 日                                                           |
| hour      | int      | 时                                                           |
| minute    | int      | 分                                                           |
| second    | int      | 秒                                                           |
| week      | int      | 星期<br />0~6， 表示星期一到星期天                           |
| time_zone | int      | 用24时区的，手机端的获取时区是整数<br />0-12东，13-24西,需要功能表支持 |

`交互结构体内容：`

```c
//系统时间
struct protocol_set_time
{
	struct protocol_head head;//0x3,0x1
	uint16_t year;
	uint8_t month;
	uint8_t day;
	uint8_t hour;
	uint8_t minute;
	uint8_t second;
	uint8_t week;
	uint32_t utc_time;  //暂时不用兼容硬件部分代码
  
  /* 
  bool v2_support_set_time_zone_float_03_01;//支持世界时钟设备在有此功能表的情况下时间设置中 time_zone为浮点型，小数点后有两位，app此时的时区设定值为实际时区值的扩大一百倍 ，无此功能表则按实际时区值下发
  */
	uint16_t time_zone; //用24时区的，手机端的获取时区是整数，0-12东，13-24西
};
```

`设置时间的json示例：`

```json
{
	"year": 2022,
	"monuth": 12,
	"day": 16,
	"hour": 17,
	"minute": 49,
	"second": 46,
	"week": 5,
	"time_zone": 8
}
```

`设置时间的字节数据：`

```c
[0x3,0x1,0xe6,0x7,0xc,0x10,0x11,0x31,0x2e,0x5,0x8]
```



#### **设备/模拟器发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd; //0x3
  uint8_t key; //0x1
};
```

`回复APP设置运动目标的示例：`

无

`回复APP设置运动目标字节数据：`

```c
[0x3,0x1]
```

