### 获取错误记录

#### 事件号：320

#### APP端发送：

`发送json字段：`

| 字段名 | 字段类型 | 字段说明                     |
| ------ | -------- | ---------------------------- |
| type   | int      | 0 查询<br />1 清除记录 |

`交互结构体内容：`

```c
struct protocol_get_error_record
{
  struct protocol_head head;
  uint8_t type; // 0x00 查询,0x01 清除记录
};
```

`获取错误记录json示例：`

```json
{
  "type" : 0
}
```

`获取错误记录字节数据：`

```c
[0x2,0x40,0x0]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| type       | int      | 0 查询<br />1 清除记录                                 |
| reset_flag | int      | 0 正常<br />1 硬错误(Hard Faul)<br />2 看门狗服务<br />3 断言复位<br />4 掉电服务<br />5 其他异常 |
| hw_error   | int      | 硬件错误码 <br />0 正常<br />1 加速度错误<br />2 心率错误<br />3 TP错误<br />4 flash错误 |

`交互结构体内容：`

```c
struct protocol_get_error_record_reply
{
  struct protocol_head head;
  uint8_t type; 			//0x00:查询 0x01:清除记录
  uint8_t reset_flag;	//0x00:正常 0x01:硬错误(Hard Faul) 0x02:看门狗服务 0x03:断言复位 0x04:掉电服务 0x05:其他异常
  uint8_t hw_error;	  //硬件错误码 0:正常 0x01:加速度错误 0x02:心率错误 0x03:TP错误 0x04:flash错误
};
```

`回复获取错误信息示例：`

```json
{
  "type":0,
  "reset_flag":0,
  "hw_error":0
}
```

`回复获取错误信息字节数据：`

```c
[0x2,0x40,0x0,0x0,0x0]
```

