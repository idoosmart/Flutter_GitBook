### 设置一键呼叫

#### 事件号：119

#### APP端发送：

`发送json字段：`

| 字段名     | 字段类型 | 字段说明                                       |
| ---------- | -------- | ---------------------------------------------- |
| on_off     | int      | 开关<br />1 开 <br />0 关                      |
| phone_type | int      | 0：无效 <br />1：doro手机  <br />2：非doro手机 |

`交互结构体内容：`

```c
//设置一键呼叫开关
struct protocol_set_onekey_sos
{
  struct protocol_head head;//0x3,0x2c
  uint8_t on_off;     //0xAA 开,0x55 关
  uint8_t phone_type; //0x00:无效 0x01:doro手机  0x02：非doro手机
};
```

`设置一键呼叫开关json示例：`

```json
{
  "on_off": 1,
  "phone_type" : 0
}
```

`设置一键呼叫开关字节数据：`

```c
[0x3,0x2c,0xaa,0x0]
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
  struct protocol_head head;//0x03,0x2c
  uint8_t status_code;
};
```

`回复设置一键呼叫开关json示例：`

```json
{
  "status_code" : 0
}
```

`回复设置一键呼叫开关字节数据：`

```c
[0x3,0x2c]
```

