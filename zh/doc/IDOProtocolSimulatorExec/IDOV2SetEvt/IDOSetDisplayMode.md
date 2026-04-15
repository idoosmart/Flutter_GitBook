### 设置显示模式

#### 事件号：108

#### **APP端发送**：

`发送json字段`

| 字段名 | 字段类型 | 字段说明                                                  |
| ------ | -------- | --------------------------------------------------------- |
| mode   | int      | 模式<br />0:默认<br />1:横屏<br />2:竖屏<br />3:翻转180度 |

`交互结构体内容：`

```c
//显示模式
struct protocol_display_mode
{
    struct protocol_head head;
    uint8_t mode;
};
```

`设置显示模式json示例：`

```json
{
  "mode": 0
}
```

`设置显示模式字节数据：`

```c
[0x03,0x2B,0x0]
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
  struct protocol_head head;//0x03,0x2B
  uint8_t status_code;
};
```

`回复APP设置显示模式json示例：`

```json
{
  "status_code" : 0
}
```

`回复APP设置显示模式字节数据：`

```c
[0x03,0x2B,0x0]
```

