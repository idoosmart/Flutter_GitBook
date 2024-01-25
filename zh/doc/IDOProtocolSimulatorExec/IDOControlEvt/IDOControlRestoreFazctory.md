### 控制设备恢复出厂

#### 事件号:408

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x4
};
```

`控制设备恢复出厂json示例：`

无

`控制设备恢复出厂字节数据：`

```c
[0xf0,0x4]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd;//0xf0
  uint8_t key;//0x4
};
```

`回复控制设备恢复出厂json示例：`

无

`回复控制设备恢复出厂字节数据：`

```c
[0xf0,0x4]
```

