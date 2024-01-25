### 控制关闭设备

#### 事件号:406

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x3
};
```

`控制关闭设备json示例：`

无

`控制关闭设备字节数据：`

```c
[0xf0,0x3]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x3
};
```

`回复控制关闭设备json示例：`

无

`回复控制关闭设备字节数据：`

```c
[0xf0,0x3]
```

