### 获取HID信息

#### 事件号：310

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_get
{
  struct protocol_head head;//0x02,0xa2
};
```

`获取HID信息json示例：`

无

`获取HID信息字节数据：`

```c
[0x2,0xa2]
```



#### **设备/模拟器发送**：

`发送json字段：`

| 字段名   | 字段类型 | 字段说明                 |
| -------- | -------- | ------------------------ |
| is_start | int      | 0没有启动<br />1启动成功 |

`交互结构体内容：`

```c
struct protocol_get_hid_info_reply
{
  struct protocol_head head;//0x2,0xa2
  uint8_t is_start;   //0没有启动,1启动成功
};
```

`回复获取HID信息json示例：`

```json
{
  "is_start" : 0
}
```

`回复获取HID信息字节数据：`

```c
[0x2,0xa2,0x0]
```

