### 设置音乐开关

#### 事件号：117

#### **APP端发送**：

`发送json字段：`

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| on_off           | int      | 开关<br />1 开 <br />0 关                                    |
| show_info_status | int      | 展示歌曲信息开关<br />1:开 <br />0:关<br />需要固件开启功能表支持`supportV2SetShowMusicInfoSwitch` |

`交互结构体内容：`

```c
//音乐开关
struct protocol_music_onoff
{
    struct protocol_head head;//0x3,0x2a
    uint8_t switch_status;
    uint8_t show_info_status;//展示歌曲信息开关 0xAA:开 0x55:关  0无效默认开启,需要功能表支持support_v2_set_show_music_info_switch_03_2A
};
```

`设置音乐开关json示例：`

```json
{
  "on_off":1
}
```

`设置音乐开关字节数据：`

```c
[0x3,0x2a,0xaa,0x0]
```



#### 设备/模拟器发送：

`发送json字段：`

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`交互结构体内容：`

```c
struct protocol_reply
{
  struct protocol_head head;//0x03,0x2a
  uint8_t status_code;
};
```

`回复设置音乐开关json示例：`

```json
{
  "status_code" : 0
}
```

`回复设置音乐开关字节数据：`

```c
[0x3,0x2a,0x0]
```

