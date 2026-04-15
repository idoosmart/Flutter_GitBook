### 设置ota授权

#### 事件号:407

#### APP端发送：

`发送json字段：`

| 字段名    | 字段类型 | 字段说明                                          |
| --------- | -------- | ------------------------------------------------- |
| device_id | int      | 设备ID                                            |
| version   | int      | 版本0 表示不进行版本校验,用于不能降级的约束,默认0 |

`交互结构体内容：`

```c
struct protocol_ota_auth
{
  struct protocol_head head;
  uint16_t device_id; //设备ID
  uint8_t version;    //版本0 表示不进行版本校验,用于不能降级的约束,默认0
};
```

`设置OTA授权json示例：`

```json
{
    "device_id" : 0,
    "version" : 0
}
```

`设置OTA授权字节数据：`

```c
[0x1,0x3,0x0,0x0]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| err_code | int      | 错误码<br />0：校验成功<br />1：ID号校验失败<br />2：版本号校验失败<br />3：电量不足<br />4：其他错误 |

`交互结构体内容：`

```c
struct protocol_ota_auth_reply
{
    struct protocol_head head;
    uint8_t err_code;   //0x00校验成功,0x01 ID号校验失败,0x02 版本号校验失败,0x03 电量不足,0x04 其他错误
};
```

`回复设置OTA授权json示例：`

```json
{
    "err_code" : 0
}
```

`回复设置OTA授权字节数据：`

```c
[0x1,0x3,0x0]
```

