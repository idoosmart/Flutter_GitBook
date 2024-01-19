### 获取下载语言支持


功能表:getDownloadLanguage

**Flutter示例：**

```dart
/// 获取下载语言支持事件号
getDownLanguage(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_down_language),

/// 获取下载语言支持
libManager.send(evt: CmdEvtType.getDownLanguage, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                           |
| ---------------- | -------- | ---------------------------------- |
| use_lang         | int      | 当前使用的语言                     |
| default_lang     | int      | 默认语言                           |
| fixed_lang       | int      | 固定存储语言个数                   |
| max_storage_lang | int      | 最大存储语言                       |
| lang_array       | 集合     | 已经存储语言值列表集合 value的集合 |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| value  | int [14] | 已经存储语言值<br />前default_fixed_lang返回是固件固定的，遇0结束 |

`示例：`

```c
{
  "use_lang" : 27,
  "default_lang" : 285,
  "fixed_lang" : 132,
  "max_storage_lang" : 0,
  "lang_array":[
  {
      "type":1
  },
  {
      "type":2
  },
  {
      "type":3
  },
  {
      "type":4
  },
  {
      "type":5
  },
  {
      "type":6
  },
  {
      "type":7
  },
  {
      "type":8
  }]
 }
```
