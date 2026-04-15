### 获取通知中心开关

#### 事件号：306

#### APP端发送：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_get
{
  struct protocol_head head;//0x02,0x10
};
```

`获取通知中心开关json示例：`

无

`获取通知中心开关字节数据：`

```c
[0x2,0x10]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| notify_switch  | int      | 通知提醒开关<br />0：总开关关(预留 无效功能)<br />1：ble总开关开(发起配对 IOS专用)<br />2：设置子开关<br />3：只开bt（开关）<br />4：ble、bt都开（开关）<br />-1：无效 |
| call_switch    | int      | 来电子提醒开关 <br />1:开<br />0:关<br />-1:无效             |
| notify_item1   | int      | 子应用开关1 每个bit代表一个应用                              |
| notify_item2   | int      | 子应用开关2 每个bit代表一个应用                              |
| call_delay     | int      | 来电提醒延时 单位秒                                          |
| notify_item3   | int      | 子应用开关3 每个bit代表一个应用                              |
| notify_item4   | int      | 子应用开关4 每个bit代表一个应用                              |
| notify_item5   | int      | 子应用开关5 每个bit代表一个应用                              |
| notify_item6   | int      | 子应用开关6 每个bit代表一个应用                              |
| notify_item7   | int      | 子应用开关7 每个bit代表一个应用                              |
| notify_item8   | int      | 子应用开关8 每个bit代表一个应用                              |
| notify_item9   | int      | 子应用开关9 每个bit代表一个应用                              |
| notify_item10  | int      | 子应用开关10 每个bit代表一个应用                             |
| msg_all_switch | int      | 消息应用总开关 <br />1:开<br />0:关<br />-1:无效(不支持)     |
| notify_item11  | int      | 子应用开关11 每个bit代表一个应用                             |
| notify_item12  | int      | 子应用开关12 每个bit代表一个应用                             |

`回复APP获取通知中心json示例：`

```json
{
	"call_delay" : 0,
	"call_switch" : 1,
	"msg_all_switch" : -1,
	"notify_item1" : 0,
	"notify_item10" : 0,
	"notify_item11" : 0,
	"notify_item12" : 0,
	"notify_item2" : 0,
	"notify_item3" : 0,
	"notify_item4" : 0,
	"notify_item5" : 0,
	"notify_item6" : 0,
	"notify_item7" : 0,
	"notify_item8" : 0,
	"notify_item9" : 0,
	"notify_switch" : 0
}
```

`回复APP获取通知中心字节数据：`

```c
[0x2,0x10,0xAA,0x0,0x0,0x55,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0,0x0]
```

