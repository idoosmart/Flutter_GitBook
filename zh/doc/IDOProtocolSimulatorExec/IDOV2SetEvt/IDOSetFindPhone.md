### 设置寻找手机

#### 事件号：103

#### **APP端发送**:

`发送json字段：`

| 字段名 | 字段类型 | 字段说明               |
| ------ | -------- | ---------------------- |
| on_off | int      | 1:打开<br />0:关闭 |

`交互结构体内容：`

```c
//寻找手机
struct protocol_find_phone
{
    struct protocol_head head;
    uint8_t status;
    uint8_t timeout;
};
```

`设置寻找手机json示例：`

```json
{
   "on_off": 1
}
```

`设置寻找手机字节数据：`

```c
[0x03,0x26,0xAA]
```



#### **设备/模拟器发送**：

`发送json字段：`

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`交互结构体内容：`

```c
struct protocol_reply
{
  struct protocol_head head;//0x03,0x26
  uint8_t status_code;
};
```

`回复APP设置寻找手机json示例：`

```json
{
    "status_code" : 0
}
```

`回复APP设置寻找手机字节数据：`

```c
[0x03,0x26,0x0]
```

