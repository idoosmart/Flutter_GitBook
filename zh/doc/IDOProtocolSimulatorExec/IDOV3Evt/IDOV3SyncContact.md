### V3同步协议蓝牙通话常用联系人


功能表:setSyncContact,reminderCallContact 【getSupportSetGetEmergencyContactV3】

**Flutter示例：**

```dart
/// 同步常用联系人事件号
setSyncContact(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.tran_json_sync_contact
),

/// 同步常用联系人
libManager.send(evt: CmdEvtType.setSyncContact, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| version   | int      | 协议库版本号                                                 |
| operat    | int      | 操作 <br />0：无效<br />1：设置联系人<br />2：查询联系人 <br />3：设置紧急联系人 需要功能表支持`getSupportSetGetEmergencyContactV3`<br />4：查询紧急联系人 需要功能表支持`getSupportSetGetEmergencyContactV3` |
| items_num | int      | 联系人详情个数 最大默认支持10个 <br />可以通过获取事件号**getSupportMaxSetItemsNum**获取字段`contact_max_set_num`，读取设备支持的常用联系人最大设置数量 |
| items     | 集合     | 联系人详情 `phone` & `name`的集合                            |

| 字段名 | 字段类型 | 字段说明                                     |
| ------ | -------- | -------------------------------------------- |
| phone  | char []  | 联系人号码内容 最大支持14个字节 + '\0'换行符 |
| name   | char []  | 联系人名称内容 最大支持31个字节 + '\0'换行符 |

`示例：`

```c
{
    "version":0,
    "operat":1,
    "items_num":1,
    "items":[
        {
            "phone":"13310214520",
            "name":"张三"
        }
    ]
}
```

**App收到的json字段**：

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| version   | int      | 协议库版本号                                                 |
| err_code  | int      | 错误码 0成功，非0是错误码                                    |
| operat    | int      | 操作 <br />0：无效<br />1：设置<br />2：查询<br />3：设置紧急联系人 需要功能表支持`getSupportSetGetEmergencyContactV3`<br />4：查询紧急联系人 需要功能表支持`getSupportSetGetEmergencyContactV3` |
| items_num | int      | 联系人详情个数 最大支持10个<br /><br />联系人详情个数 最大默认支持10个 <br />可以通过获取事件号**getSupportMaxSetItemsNum**获取字段`contact_max_set_num`，读取设备支持的常用联系人最大设置数量<br />操作码(operat)是查询(2/4)有效 |
| items     | 集合     | 联系人详情 phone & name的集合<br />操作码(operat)是查询(2/4)有效 |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| phone  | char []  | 联系人号码内容 最大支持14个字节 + '\0'换行符<br />操作码(operat)是查询(2/4)有效 |
| name   | char []  | 联系人名称内容 最大支持31个字节 + '\0'换行符<br />操作码(operat)是查询(2/4)有效 |

`示例：`

```c
{
    "version":0,
    "err_code":0,
    "operat":1,
    "items_num":0,
    "items":null
}
```

