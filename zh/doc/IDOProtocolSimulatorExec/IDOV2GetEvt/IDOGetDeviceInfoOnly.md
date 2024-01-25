### 获取设备信息

#### 事件号:301

#### **APP端发送**：

`发送json字段：`

无

`交互结构体内容：`

```c
struct protocol_get
{
  struct protocol_head head;//0x02,0x01
};
```

`获取设备信息json示例：`

无

`获取设备信息字节数据：`

```c
[0x2,0x1]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名                         | 字段类型 | 字段说明                                                     |
| ------------------------------ | -------- | ------------------------------------------------------------ |
| deivce_id                      | int      | 设备id                                                       |
| firmware_version               | int      | 版本号                                                       |
| mode                           | int      | 模式<br />0：运动模式，<br />1：睡眠模式               |
| batt_status                    | int      | 电池状态 <br />0： 正常<br />1：正在充电<br />2：充满<br />3：低电量 |
| energe                         | int      | 电量等级                                                     |
| pair_flag                      | int      | 绑定状态                                                     |
| reboot                         | int      | 是否重启 <br />如果重启 app会再次同步配置信息给手环          |
| bind_confirm_method            | int      | 绑定确认方式 <br />0：默认(注意以前ID号定制),超时时间无效<br />1：单击[按键在下面]<br />2：为长按[按键在下面]<br />3：屏幕点击 横向确认和取消,确认在左边<br />4：屏幕点击 横向确认和取消,确认在右边<br />5：屏幕点击 竖向确认和取消，确认在上边<br />6：屏幕点击 竖向确认和取消，确认在下边<br />7：点击(右边一个按键) |
| bind_confirm_timeout           | int      | 超时时间<br />最长为15秒 0表示不超时                         |
| platform                       | int      | 手环的平台 <br />0   ：nordic<br />10 ：realtek 8762x <br />20 ：cypress psoc6<br />30：Apollo3 <br />40：为汇顶  <br />50：nordic+泰凌微, 瑞坤 <br />80：5340   <br />90：炬芯 |
| shape                          | int      | 0：默认（gt01 方形的）<br />1：圆形<br />2：方形的<br />3：椭圆 |
| dev_type                       | int      | 0：默认（gt01 手表）<br />1： 手环<br />2：手表              |
| user_defined_dial_main_version | int      | 自定义表盘主版本 从1开始  <br />0：不支持对应的自定义表盘功能 |
| cloud_clock_dial_version       | int      | 云端表盘版本号 默认从0开始 <br />是否支持云端表盘有对应的功能表multi_dial (废弃 同user_defined_dial_main_version ) |
| show_bind_choice_ui            | int      | 固件绑定时候显示勾勾叉叉ui界面  app根据这个位显示提示固件点击绑定  <br />0：不需要app提示  1：需要app提示 |
| bootload_version               | int      | nordic平台bootloader版本信息  最小为1                        |

`交互结构体内容：`

```c
//获取信息类
struct protocol_device_info
{
  struct protocol_head head;//0x2,0x1
  uint16_t device_id;   //设备id
  uint8_t version;      //版本号
  uint8_t mode;         //模式
  uint8_t batt_status;  //电池状态  电池状态 （0x00： 正常， 0x01：正在充电，0x02：充满， 0x03：低电量）
  uint8_t batt_level;   //电量等级
  uint8_t pair_flag;    //绑定状态
  uint8_t reboot_flag;  //是否重启 ,如果重启，app会再次同步配置信息给手环
  uint8_t version_info; //是否存在版本信息;

  uint8_t bind_confirm_method;
  /**
         * 绑定确认方式 低4位为确认方式 &0x0f,
         * 0x00默认(注意以前ID号定制),超时时间无效,
         * 0x01(单击[按键在下面]),
         * 0x02(为长按[按键在下面]),
         * 0x03(屏幕点击 横向确认和取消,确认在左边),
         * 0x04(屏幕点击 横向确认和取消,确认在右边)，
         * 0x05(屏幕点击 竖向确认和取消，确认在上边)，
         * 0x06(屏幕点击 竖向确认和取消，确认在下边,
         * 0x07点击(右边一个按键))
         * 高4位为超时时间 &0xf0,最长为15秒,0表示不超时
        **/

  uint8_t platform;  
  /**
         * 手环的平台 
         * 0:nordic
         * 10:realtek 8762x
         * 20:cypress psoc6
         * 30:Apollo3    
         * 40:汇顶
         * 50:nordic+泰凌微
         * 60:泰凌微+5340+no nand flash(需要ota模式)
         * 70:汇顶+富瑞坤  
         * 80:5340  
         * 90:炬芯 
         * 99:思澈
         */
  uint8_t shape;     // 0:默认(gt01方形的) 1:圆形 2:方形的 3:椭圆
  uint8_t dev_type;  // 0:默认(gt01手表) 1:手环 2:手表
  uint8_t user_defined_dial_main_version;//自定义表盘主版本 从1开始 0:不支持对应的自定义表盘功能
  uint8_t cloud_clock_dial_version;//云端表盘版本号 默认从0开始，是否支持云端表盘有对应的功能表multi_dial (废弃 同user_defined_dial_main_version )
  uint8_t show_bind_choice_ui;     //固件绑定时候显示勾勾叉叉ui界面，app根据这个位显示提示固件点击绑定 0:不需要app提示 1:需要app提示
  uint8_t bootload_version;        //nordic平台bootloader版本信息 最小为1
};
```

`回复APP获取设备信息的json示例：`

```c

	"batt_status" : 0,
	"bind_confirm_method" : 0,
	"bind_confirm_timeout" : 0,
	"bootload_version" : 0,
	"cloud_clock_dial_version" : 5,
	"deivce_id" : 7698,
	"dev_type" : 2,
	"energe" : 56,
	"firmware_version" : 1,
	"mode" : 1,
	"pair_flag" : 1,
	"platform" : 90,
	"reboot" : 0,
	"shape" : 2,
	"show_bind_choice_ui" : 0,
	"user_defined_dial_main_version" : 5
}
```

`回复APP获取设备信息的字节数据：`

```c
[0x2,0x1,0x12,0x1E,0x1,0x1,0x0,0x38,0x1,0x0,0x1,0x0,0x5A,0x2,0x2,0x3,0x5,0x0,0x0,0x0]
```

