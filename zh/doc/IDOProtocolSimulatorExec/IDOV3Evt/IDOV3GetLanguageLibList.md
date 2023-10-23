### V3获取设备字库列表


功能表:getLangLibraryV3

**Flutter示例：**

```dart
/// v3获取设备字库列表事件号
getLanguageLibraryDataV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_language_library_data),

/// v3获取设备字库列表
libManager.send(evt: CmdEvtType.getLanguageLibraryDataV3, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| version          | int      | 协议库版本号<br />预留                                       |
| use_lang         | int      | 当前使用的语言                                               |
| default_lang     | int      | 默认语言                                                     |
| fixed_lang       | int      | 固定存储语言个数                                             |
| max_storage_lang | int      | 最大存储语言                                                 |
| items_len        | int      | 目前固件支持的语言个数<br />可能没有对应的字库文件           |
| user_len         | int      | 目前已经储存的语言个数                                       |
| items            | 集合     | 目前固件支持的语言个数详情集合<br />language_type & language_version的集合 |
| items_user       | 集合     | 目前已经储存的语言个数详情集合<br />language_type & language_version的集合 |

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| language_type    | int      | 语言类型<br />0 ：无效 <br />1 ：中文<br />2 ：英文 <br />3 ：法语<br />4 ：德语 <br />5 ：意大利语 <br />6 ：西班牙语<br />7 ：日语 <br />8 ：波兰语 <br />9 ：捷克语<br />10 ：罗马尼亚 <br />11 ：立陶宛语 <br />12 ：荷兰语<br />13 ：斯洛文尼亚语<br />14 ：匈牙利语<br />15 ： 俄罗斯语<br />16 ：乌克兰语  <br />17 ：斯洛伐克语  <br />18 ：丹麦语  <br />19 ：克罗地亚语<br />20 ：印尼语<br />21 ：韩语<br />22 ：印地语<br />23 ：葡萄牙语 <br />24 ：土耳其语<br />25 ：泰国语 <br />26 ：越南语<br />27 ：缅甸语<br />28 ：菲律宾语<br />29：繁体中文<br />30 ：希腊语<br />31 ：阿拉伯语<br />32 ：瑞典语<br />33 ：芬兰语<br />34 ：波斯语<br />35 ：挪威语 |
| language_version | int      | 语言版本号                                                   |

`示例：`

```c
{
    "version":0,
    "use_lang":1,
    "default_lang":1,
    "fixed_lang":3,
    "max_storage_lang":10,
    "items_len":2,
    "user_len":3,
    "items":[
        {
            "language_type":1,
            "language_version":0
        },
        {
            "language_type":2,
            "language_version":0
        }
    ],
    "items_user":[
        {
            "language_type":1,
            "language_version":0
        },
        {
            "language_type":2,
            "language_version":0
        },
        {
            "language_type":3,
            "language_version":0
        }
    ]
}
```
