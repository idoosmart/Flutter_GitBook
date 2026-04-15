### 设置用户信息

#### 事件号：107

#### **APP端发送**：

`发送json字段：`

| 字段名 | 字段类型 | 字段说明                        |
| ------ | -------- | ------------------------------- |
| year   | int      | 出生日期 年                     |
| month  | int      | 出生日期 月                     |
| day    | int      | 出生日期 日                     |
| height | int      | 身高 单位厘米                   |
| weight | int      | 体重 单位千克 值需要x100|
| gender | int      | 性别<br />1：女 <br />0：男 |

`交互结构体内容：`

```c
//用户信息
struct protocol_set_user_info
{
    struct protocol_head head;//0x3,0x10
    uint8_t height;     //身高
    uint16_t weight;    //体重
    uint8_t gender;
    uint16_t year;      //生日
    uint8_t month;
    uint8_t day;
};
```

`设置用户信息json示例：`

```json
{
	"year": 2022,
	"monuth": 12,
	"day": 16,
	"heigh": 173,
	"weigh": 7400,
	"gender": 0
}
```

`设置用户信息的字节数据：`

```c
[0x3,0x10,0xad,0xe8,0x1c,0x0,0x0,0xe6,0x7,0xc,0x10]
```



#### 设备/模拟器发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_head
{
  uint8_t cmd; //0x3
  uint8_t key; //0x10
};
```

`回复设置用户信息json示例：`

无

`回复设置用户信息字节数据：`

```c
[0x03,0x10]
```

