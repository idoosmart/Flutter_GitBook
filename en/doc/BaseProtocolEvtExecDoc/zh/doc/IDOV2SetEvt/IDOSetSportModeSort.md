### 设置运动模式排序


功能表：setSportModeSort

**Flutter示例：**

```dart
/// 设置运动模式排序事件号
setSportModeSort(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_sport_mode_sort),

/// 设置运动模式排序
libManager.send(evt: CmdEvtType.setSportModeSort, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                            |
| ------ | -------- | ----------------------------------- |
| items  | 集合     | 运动模式排序详情 index & type的集合 |

| 字段名 | 字段类型 | 字段说明                                       |
| ------ | -------- | ---------------------------------------------- |
| index  | int      | 排序<br />从1开始 0无效                        |
| type   | int      | 运动模式类型<br />1 走路<br />2  跑步 .. |

`示例：`

```c
{
  "item": [
  {
    "index": 1,
    "type": 0
  },
  {
    "index": 2,
    "type": 2
  },
  {
    "index": 3,
    "type": 4
  },
  {
    "index": 4,
    "type": 8
  },
  {
    "index": 5,
    "type": 85
  },
  {
    "index": 6,
    "type": 78
  },
  {
    "index": 7,
    "type": 45
  },
    {
      "index": 8,
      "type": 65
    }
  ]
}
```
