### V3获取固件本地提示音文件信息


功能表:getSupportGetBleBeepV3

**Flutter示例：**

```dart
/// v3获取固件本地提示音文件信息事件号
getBleBeepV3(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_ble_beep
),

/// v3获取固件本地提示音文件信息
libManager.send(evt: CmdEvtType.getBleBeepV3, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                    |
| ---------- | -------- | --------------------------- |
| version    | int      | 协议版本号                  |
| err_code   | int      | 错误码 0成功 非0失败        |
| item_count | int      | 提示音个数                  |
| item       | 集合     | 提示音文件名列表 name的集合 |

| 字段名 | 字段类型 | 字段说明                    |
| ------ | -------- | --------------------------- |
| name   | char []   | 提示音文件名 最大值30个字节 |

`示例：`

```c
{
    "version":0,
    "err_code":0,
    "item_count":2,
    "item":[
        {
            "name":" "
        },
        {
            "name":" "
        }
    ]
}
```
