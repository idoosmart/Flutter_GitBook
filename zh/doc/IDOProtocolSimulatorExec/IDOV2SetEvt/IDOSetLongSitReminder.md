### 设置久坐提醒

#### 事件号:101

#### APP端发送：

`发送json字段：`

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| start_hour   | int      | 开始时间 时                                                  |
| start_minute | int      | 开始时间 分                                                  |
| end_hour     | int      | 结束时间 时                                                  |
| end_minute   | int      | 结束时间 分                                                  |
| interval     | int      | 间隔 <br />取值应大于15分钟 单位分钟                         |
| repetitions  | int      | 重复及开关<br /> bit0 ：0表示关 1表示开 <br />bit1-7  : 0表示不重复，1表示重复 |

`交互结构体内容：`

```c
struct protocol_long_sit
{
	struct protocol_head head;//0x03,0x20
	uint8_t start_hour;    //开始时间 晚上勿扰
	uint8_t start_minute;
	uint8_t end_hour;
	uint8_t end_minute;    //结束时间
	uint16_t interval;     //间隔
	uint16_t repetitions;  //重复

};
```

`设置久坐提醒信息json示例：`

```json
{
	"start_hour": 15,
	"start_minute": 40,
	"end_hour": 23,
	"end_minute": 26,
	"interval": 15,
	"repetitions": 254
}
```

`设置久坐提醒信息字节数据：`

```c
[0x03,0x20,0xf,0x28,0x17,0x1a,0xf,0x0,0xfe,0x0]
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
  struct protocol_head head;//0x03,0x20
  uint8_t status_code;
};
```

`回复APP设置久坐提醒信息json示例：`

```json
{
  "status_code": 0
}
```

`回复APP设置久坐提醒信息字节数据：`

```c
[0x03,0x20,0x0]
```


