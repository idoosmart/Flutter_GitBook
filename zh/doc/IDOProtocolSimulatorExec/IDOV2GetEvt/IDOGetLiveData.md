### 获得实时数据

#### 事件号：304

#### APP端发送：

`发送json字段：`

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| flag   | int      | 0：无功能<br />1：强制打开心率监测<br />2：强制打开血压监测 |

`交互结构体内容：`

```c
//实时数据
struct protocol_get_live_data
{
	struct protocol_head head;//0x2,0xa0
	uint8_t flag; 
};
```

`获取实时数据json示例：`

```json
{
  "flag" : 1
}
```

`获取实时数据字节数据：`

```c
[0x2,0xa0,0x1]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名            | 字段类型 | 字段说明                                             |
| ----------------- | -------- | ---------------------------------------------------- |
| total_step        | int      | 总步数                                               |
| total_calories    | int      | 总卡路里 <br />单位大卡                              |
| total_distances   | int      | 总距离 <br />单位m                                   |
| total_active_time | int      | 总活动时长<br />单位秒                               |
| heart_rate        | int      | 心率数据<br />单位bpm<br />如果没有心率功能，该值为0 |

`交互结构体内容：`

```c
struct protocol_get_live_data_reply
{
	struct protocol_head head;
	uint32_t step;
	uint32_t calories;
	uint32_t distances;
	uint32_t active_time;
	uint8_t  heart_rate;
};
```

`回复APP获取实时数据json示例：`

```c
{
  "heart_rate" : 0,
  "total_active_time" : 0,
  "total_calories" : 0,
  "total_distances" : 0,
  "total_step" : 0
}
```

`回复APP获取实时数据字节数据：`

```c
[0x2,0xa0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0]
```

