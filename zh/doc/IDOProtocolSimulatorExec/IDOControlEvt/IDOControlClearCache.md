### 控制清除手环缓存

#### 事件号:409

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x5
};
```

`控制控制清除手环缓存json示例：`

无

`控制清除手环缓存字节数据：`

```c
[0xf0,0x5]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名     | 字段类型 | 字段说明              |
| ---------- | -------- | --------------------- |
| is_success | int      | 1：成功 <br />0：失败 |

`交互结构体内容：`

```c
struct protocol_set_reply
{
  struct protocol_head head;//0xf0,0x5
    uint8_t is_success; // 1：成功 ， 0失败
};
```

`回复控制清除手环缓存json示例：`

```json
{
    "is_success" : 0
}
```

`回复控制清除手环缓存字节数据：`

```c
[0xf0,0x5,0x1]
```
