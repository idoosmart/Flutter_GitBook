### 控制设备断线

#### 事件号:404

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x2
};
```

`控制设备断线json示例：`

无

`控制设备断线字节数据：`

```c
[0xf0,0x2]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x2
};
```

`回复控制设备断线json示例：`

无

`回复控制设备断线字节数据：`

```c
[0xf0,0x2]
```

