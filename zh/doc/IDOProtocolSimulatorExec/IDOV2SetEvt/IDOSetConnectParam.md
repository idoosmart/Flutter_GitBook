### 设置控制连接参数


**Flutter示例：**

```dart
/// 控制连接参数事件号
setConnParam(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_conn_param),

/// 控制连接参数
libManager.send(evt: CmdEvtType.setConnParam, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| mode              | int      | 1：控制 <br />2：查询                                        |
| modify_conn_param | int      | 1：开启log<br />2：关闭log<br />3：agps写入<br />4：agps 擦除<br />5：gps_fw 写入 |
| max_interval      | int      | 最大间隔<br />单位秒                                         |
| min_interval      | int      | 最小间隔<br />单位秒                                         |
| slave_latency     | int      | 从设备延迟<br />0-499包<br />设备不回复APP的包数             |
| conn_timeout      | int      | 连接超时<br />单位秒                                         |

`示例：`

```c
{
    "mode":2,
    "modify_conn_param":0,
    "max_interval":0,
    "min_interval":0,
    "slave_latency":0,
    "conn_timeout":0
}
```


**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                           |
| -------- | -------- | -------------------------------------------------- |
| cur_mode | int      | 当前模式<br />1 设置快速模式<br />2 慢速模式 |
| err_code | int      | 成功0  非0失败                                  |

`示例：`

```c
{
    "cur_mode":2,
    "err_code":0
}
```

