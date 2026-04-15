### 获取GPS信息

#### 事件号：312

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_get
{
  struct protocol_head head;//0x02,0xa3
};
```

`获取GPS信息json示例：`

无

`获取GPS信息字节数据：`

```c
[0x2,0xa3]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名        | 字段类型 | 字段说明                                                  |
| ------------- | -------- | --------------------------------------------------------- |
| err_code      | int      | GPS是否错误<br />0正常 非0异常                            |
| fw_version    | int      | GPS固件版本                                               |
| agps_info     | int      | AGPS有效期                                                |
| agps_err_code | int      | AGPS错误值                                                |
| utc_year      | int      | utc时间 年                                                |
| utc_month     | int      | utc时间 月                                                |
| utc_day       | int      | utc时间 日                                                |
| utc_hour      | int      | utc时间 时                                                |
| utc_minute    | int      | utc时间 分                                                |
| start_mode    | int      | 启动模式<br />1 冷启动<br />2 热启动                      |
| gns           | int      | 定位星选择<br />1 GPS<br />2 GLONASS<br />3 GPS + GLONASS |
| fix_start_bit | int      | 修正标识位<br />默认0 用于调试                            |

`回复获取GPS信息json示例：`

```json
{
	"err_code": 0,
	"fw_version": 66051,
	"agps_info": 0,
	"agps_err_code": 0,
	"utc_year": 0,
	"utc_month": 0,
	"utc_day": 0,
	"utc_hour": 0,
	"utc_minute": 0,
	"start_mode": 2,
	"gns": 0,
	"fix_start_bit": 0
}
```

`回复获取GPS信息字节数据：`

```c
[0x2,0xa3,0x0,0x3,0x2,0x1,0x0,0x0,0x0,0x0,0x0,0x0,0x0,]
```

