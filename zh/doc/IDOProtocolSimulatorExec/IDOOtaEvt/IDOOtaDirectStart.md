### 直接进入升级模式(忽略电量)

#### 事件号:401

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
 struct protocol_head
 {
   uint8_t cmd; //0x1
   uint8_t key; //0x2
 };
```

`忽略电量直接设置进入升级模式json示例：`

无

`忽略电量直接设置进入升级模式字节数据：`

```c
[0x1,0x2]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
 struct protocol_head
 {
   uint8_t cmd; //0x1
   uint8_t key; //0x2
 };
```

``回复忽略电量直接设置进入升级模式json示例：`

无

`回复忽略电量直接设置进入升级模式字节数据：`

```c
[0x1,0x2]
```

