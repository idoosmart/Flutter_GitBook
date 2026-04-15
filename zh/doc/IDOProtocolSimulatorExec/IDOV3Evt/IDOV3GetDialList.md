### V3获取表盘列表

#### 事件号：5006

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

`获取表盘列表json示例：`

无

`获取表盘列表的字节数据：`

```c
[0x33,0xDA,0xAD,0xDA,0xAD,0x01,0x0B,0x00,0x06,0x00,0x05,0x00,0x5D,0x34]
```



#### 设备/模拟器发送：

`发送json字段`：

| 字段名          | 字段类型 | 字段说明                     |
| --------------- | -------- | ---------------------------- |
| version         | int      | 协议版本号                   |
| available_count | int      | 剩余个数，可用文件个数       |
| file_max_size   | int      | 单个文件最大size 单位KB   |
| item            | 集合     | 表盘列表详情，file_name的集合 |

| 字段名    | 字段类型 | 字段说明 |
| --------- | -------- | -------- |
| file_name | char []  | 表盘名称 |

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
struct protocol_v3_file_list
{
    uint8_t  version;           //版本号
    uint16_t file_count;        //表盘已经使用数目
    uint16_t available_count;   //剩余个数，可用文件个数
    uint16_t file_max_size;		  //单个文件最大sizeKB
    char file_list[10][30];     //这里的数据用pd解包
};
uint16_t crc;
```

`回复获取表盘列表json示例：`

```c
{
  "available_count" : 4,
  "file_max_size" : 600,
  "item" : 
  [
   	{
  	 "file_name" : "custom1.iwf"
  	},
  	{
  	"file_name" : "watch253.iwf"
    }
  ],
  	"version" : 1
}
```

`回复获取表盘列表字节数据：`

```c
[33 DA AD DA AD 01 33 00 06 00 05 00 01 02 00 04 00 58 02 01 0B 00 00 00 63 75 73 74 6F 6D 31 2E 69 77 66 01 0C 00 00 00 77 61 74 63 68 32 35 33 2E 69 77 66 FD 16]

```

