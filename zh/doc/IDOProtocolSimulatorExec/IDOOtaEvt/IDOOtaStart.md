### 进入升级模式

#### 事件号:400

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
 struct protocol_head
 {
   uint8_t cmd; //0x1
   uint8_t key; //0x1
 };
```

`设置进入升级模式json示例：`

无

`设置进入升级模式字节数据：`

```c
[0x1,0x1]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| err_flag | int      | 0: 进入OTA成功 <br />1: 失败：电量过低 <br />2: 失败：设备不支持  <br>3: 失败：参数不正确 |

`回复设置进入升级模式json示例：`

```json
{
    "err_flag" : 0
}
```

`回复设置进入升级模式字节数据`

```c
[0x1,0x1,0x0]
```

