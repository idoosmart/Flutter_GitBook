### 控制设备重启

#### 事件号：403

#### APP端发送：

无



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_reply
{
  struct protocol_head head;//0xf0,0x1
  uint8_t status_code;
};
```

`回复APP设置设备重启json字段：`

```json
{
  "status_code" : 0
}
```

`回复APP设置设备重启的字节数据：`

```c
[0xf0,0x1,0x0]
```



