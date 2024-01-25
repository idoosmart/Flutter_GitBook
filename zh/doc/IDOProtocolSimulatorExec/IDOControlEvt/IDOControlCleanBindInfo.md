### 清除绑定信息

#### 事件号:405

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0x3
  uint8_t key;//0xd1
};
```

`控制设备清除绑定信息json示例：`

无

`控制设备清除绑定信息字节数据：`

```c
[0x3,0xd1]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0x3
  uint8_t key;//0xd1
};
```

`回复控制设备清除绑定信息json示例：`

无

`回复控制设备清除绑定信息字节数据：`

```c
[0x3,0xd1]
```

