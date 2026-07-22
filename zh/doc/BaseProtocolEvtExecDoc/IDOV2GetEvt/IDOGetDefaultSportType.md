### 获取默认的运动类型


功能表:setV3GetSportSortField

**Flutter示例：**

```dart
/// 获取默认的运动类型事件号
getDefaultSportType(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_default_sport_type),

/// 获取默认的运动类型
libManager.send(evt: CmdEvtType.getDefaultSportType, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                         |
| ---------------- | -------- | ------------------------------------------------ |
| default_show_num | int      | 默认显示的数量                                   |
| min_show_num     | int      | 最小支持的数量                                   |
| max_show_num     | int      | 最大支持的数量                                   |
| is_supports_sort | int      | 是否支持默认排序<br />0 不支持<br />1 支持 |
| sport_types      | 集合     | 运动类型列表集合 type的集合                      |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| type   | int [8]  | 运行类型<br />is_supports_sort=1时有效, 最大个数8个<br />空位填0 |

`示例：`

```c
{
  "default_show_num" : 27,
  "min_show_num" : 285,
  "max_show_num" : 132,
  "is_supports_sort" : 0,
  "sport_types":[
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
