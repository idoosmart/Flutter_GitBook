### 获取设备mac地址

#### 事件号：300

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_get
{
  struct protocol_head head;//0x02,0x04
};
```

`获取设备mac地址json示例：`

无

`获取设备mac地址字节数据：`

```c
[0x2,0x4]
```



#### **设备/模拟器发送**：

`发送json字段：`

| 字段名   | 字段类型 | 字段说明                 |
| -------- | -------- | ------------------------ |
| mac_addr | int [6]  | 设备的id地址 最大6个字节 |
| bt_addr  | int [6]  | bt的蓝牙地址 最大6个字节 |

`交互结构体内容：`

```c
//设备mac地址
struct protocol_device_mac
{
    struct protocol_head head;
    uint8_t mac_addr[6];
    uint8_t bt_addr[6];//bt蓝牙地址 功能表支持bool v2_get_bt_addr_02_04   
};
```

`回复APP获取设备mac地址json示例：`

```c
{
	"bt_addr" : 
	[
		244,
		3,
		18,
		255,
		132,
		212
	],
	"mac_addr" : 
	[
		244,
		3,
		18,
		255,
		132,
		212
	]
}
```

`回复APP获取设备mac地址字节数据：`

```c
[0x2,0x4,0xF4,0x3,0x12,0xFF,0x84,0xD4,0xF4,0x03,0x12,0xFF,0x84,0xD4,0x0,0x0,0x0,0x0,0x0,0x0]
```

