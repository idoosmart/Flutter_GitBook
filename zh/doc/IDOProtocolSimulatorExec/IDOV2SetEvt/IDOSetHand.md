### 设置左右手

#### 事件号：109
#### **APP端发送**：

`发送json字段：`

| 字段名 | 字段类型 | 字段说明                    |
| ------ | -------- | --------------------------- |
| hand   | int      | 0：左手 <br />1：右手 |

`交互结构体内容：`

```c
//设置左右手
struct protocol_set_handle
{
   struct protocol_head head;
   uint8_t hand_type;
};
```

`设置左右手json示例：`

```json
{
  "hand":0
}
```

`设置左右手字节数据：`

```c
[0x3,0x22,0x0]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd; //0x3
  uint8_t key; //0x22
};
```

`回复设置左右手json示例：`

无

`回复设置左右手字节数据：`

```c
[0x3,0x22]
```

