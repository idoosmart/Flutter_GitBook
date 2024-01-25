### V3获取屏幕信息

### 事件号：5007

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
uint8_t cmd = 0x33;
typedef struct protocol_v3_base
{
	uint32_t fixed;
	uint8_t version;
	uint16_t length;
	uint16_t cmd_id; 
	uint16_t nseq;
}protocol_v3_base_s;
uint16_t crc; 
```

`获取屏幕信息json示例：`

无

`获取屏幕信息的字节数据：`

```c
[33 DA AD DA AD 01 0B 00 07 00 05 00 E9 42]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名      | 字段类型 | 字段说明              |
| ----------- | -------- | --------------------- |
| width       | int      | 屏幕宽度 (像素大小) |
| height      | int      | 屏幕高度 (像素大小)       |
| format      | int      | 颜色格式              |
| sizex100    | int      | 尺寸 x100             |
| family_name | char []   | 家族名称 最大10个字节 |
| block_size  | int      | 压缩块大小            |

`交互结构体内容：`

```c
uint8_t cmd = 0x33;
typedef struct protocol_v3_base
{
	uint32_t fixed;
	uint8_t version;
	uint16_t length;
	uint16_t cmd_id; 
	uint16_t nseq;
}protocol_v3_base_s;


struct protocol_v3_watch_face_info
{
    char family_name[10];//家族名字
    uint16_t width;      //宽度像素块
    uint16_t height;     //高度像素块
    uint8_t format;      //颜色格式 < FONT_FORMAT_ARGB565(0x85) FONT_FORMAT_RGB565(5) >
    uint16_t sizex100;   //尺寸 x100
    uint16_t block_size; //压缩块大小
};
uint16_t crc;
```

`回复获取屏幕信息json示例：`

```c
{
    "block_size" : 1024,
    "family_name" : "ID206",
    "format" : 133,
    "height" : 280,
    "sizex100" : 0,
    "width" : 240
}
```

`回复获取屏幕信息字节数据：`

```c
[33 DA AD DA AD 01 1E 00 07 00 05 00 49 44 32 30 36 00 00 00 00 00 F0 00 18 01 85 00 00 00 04 B6 8E]
```

