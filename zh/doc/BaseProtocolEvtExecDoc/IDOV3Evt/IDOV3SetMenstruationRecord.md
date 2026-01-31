### 女性生理日常记录


功能表:setHistoryMenstrual 【supportPhysiologicalRecord】

**Flutter示例：**

```dart
/// 女性生理日常记录下发事件号
setMenstruationRecord(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.vbus_evt_v3_physiological_record),

/// 女性生理日常记录数据下发
libManager.send(evt: CmdEvtType.setMenstruationRecord, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名                               | 字段类型 | 字段说明                                                                                                                                                                                                       |
|-----------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| version                           | int  | 协议库版本号<br />默认0 |
| operate                           | int  | 操作类型 <br/>0:无效 <br/>1:全量设置 <br/>2:查询生理日常记录项<br/>3:查询生理日常记录数据 <br/>4:修改  <br/>5:新增 <br/>6:删除 <br/>7:获取固件修改项    |
| last_change_time                  | long | 最后一次修改的时间，操作修改 & 增加 & 删除都得更新时间，时间戳，单位：秒             |
| data_items                        | 集合   | 生理日常记录日数据列表<br />`year` & `mon` & `day & menstrual_day` & `cycle_day`的集合<br />`ovulation_interval_day` & `ovulation_before_day` & `ovulation_after_day` |
| all_items_num                     | int  | 生理日常记录日数据列表`data_items`个数                                                                                                                                                                                      |

| 字段名                    | 字段类型 | 字段说明                                                                                                       |
|------------------------|------|------------------------------------------------------------------------------------------------------------|
| year                   | int  | 记录的年                                                                                                     |
| mon                    | int  | 记录的月                                                                                                     |
| day                    | int  | 记录的日                                                                                                     |
| last_change_time       | long | 最后一次修改的时间，操作修改&增加&删除都得更新时间，时间戳，单位：秒                                      |
| change_type            | int | 修改类型，<font color='#ff0000'>获取修改项有效（operate=7）</font>   <br/>0:无效 <br/>1:新增 <br/>2:修改 <br/>3:删除，手表删除了该条数据                                      |
| items_num              | int  | 每天记录的各种类型的数据列表`items`个                                                                                           |
| items                  | 集合  | 每天记录的各种类型的数据列表<br/>`data_type` &`items_len` & `data_items`的集合                          |

| 字段名       | 字段类型 | 字段说明                                                       |
|-----------|------|------------------------------------------------------------|
| data_type | int  | 记录数据类型<br/> 0x01: 症状<br/>0x02: 点滴出血 |
| data_items  | 集合  | 记录数据子项，支持多个值，参考下表  <br /> |
| items_len  | 集合  | 记录数据子项个数  <br /> |



| 数据项类型 | 记录数据类型 | 记录数据子项类型                                               |
| ---------- | -------------- | ------------------------------------------------------------ |
| 无         | 0           |                                                              |                                                           |
| 症状       | 1           | 1：眩晕<br/>2：呕吐<br/>3：失眠<br/>4：头痛<br/>5：痤疮<br/>6：掉发<br/>7：恶心<br/>8：记忆力衰退<br/>9：腹部绞痛<br/>10：腹泻<br/>11：腹胀<br/>12：盆腔疼痛<br/>13：发冷<br/>14：浮肿<br/>15：皮肤干燥<br/>16：食欲变化<br/>17：乳房疼痛<br/>18：腰酸背痛<br/>19：心情变化<br/>20：夜间盗汗<br/>21：膀胱失禁<br/>22：便秘<br/>23：潮热<br/> | 
| 点滴出血   | 2           | 0：不出血，1：出血                                               | 



`示例：`

```json
{
  "version": 0,
  "operate":1,
  "last_change_time" : 0,
  "all_items_num": 1,
  "data_items": [
    {
      "year": 2023,
      "mon": 8,
      "day": 1,
      "items_num": 1,
      "last_change_time":0,
      "change_type":14,
      "items" :
      [
        {
          "data_type" : 1,
          "items_len" : 1,
          "data_items":[1]
        },
        {
          "data_type" : 2,
          "items_len" : 1,
          "data_items":[1]
        }
      ],
    }
  ]
}
```

**App收到的json字段**：

| 字段名                               | 字段类型 | 字段说明                                                                                                                                                                                                       |
|-----------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| version                           | int  | 协议库版本号<br />默认0 |
| operate                           | int  | 操作类型 <br/>0:无效 <br/>1:全量设置 <br/>2:查询生理日常记录项<br/>3:查询生理日常记录数据 <br/>4:修改  <br/>5:新增 <br/>6:删除 <br/>7:获取固件修改项    |
| last_change_time                  | long | 最后一次修改的时间，操作修改 & 增加 & 删除都得更新时间，时间戳，单位：秒             |
| data_items                        | 集合   | 生理日常记录日数据列表<br />`year` & `mon` & `day & menstrual_day` & `cycle_day`的集合<br />`ovulation_interval_day` & `ovulation_before_day` & `ovulation_after_day` |
| all_items_num                     | int  | 生理日常记录日数据列表`data_items`个数                                                                                                                                                                                      |

| 字段名                    | 字段类型 | 字段说明                                                                                                       |
|------------------------|------|------------------------------------------------------------------------------------------------------------|
| year                   | int  | 记录的年                                                                                                     |
| mon                    | int  | 记录的月                                                                                                     |
| day                    | int  | 记录的日                                                                                                     |
| last_change_time       | long | 最后一次修改的时间，操作修改&增加&删除都得更新时间，时间戳，单位：秒                                      |
| change_type            | int | 修改类型，<font color='#ff0000'>获取修改项有效（operate=7）</font>   <br/>0:无效 <br/>1:新增 <br/>2:修改 <br/>3:删除，手表删除了该条数据                                      |
| items_num              | int  | 每天记录的各种类型的数据列表`items`个                                                                                           |
| items                  | 集合  | 每天记录的各种类型的数据列表<br/>`data_type` &`items_len` & `data_items`的集合                          |
| configure_items_num              | int  | 支持的记录类型和数据子项`configure_items`个数个                                                                                           |
| configure_items                  | 集合  | 支持的记录类型和数据子项<br/>`data_type` &`data_value`的集合                          |

| 字段名       | 字段类型 | 字段说明                                                       |
|-----------|------|------------------------------------------------------------|
| data_type | int  | 记录数据类型<br/> 0x01: 症状<br/>0x02: 点滴出血 |
| data_items  | 集合  | 记录数据子项，支持多个值，参考下表  <br /> |
| items_len  | 集合  | 记录数据子项个数  <br /> |

| 字段名       | 字段类型 | 字段说明                                                       |
|-----------|------|------------------------------------------------------------|
| data_type | int  | 支持的记录数据类型<br/> 0x01: 症状<br/>0x02: 点滴出血 |
| data_value  | 集合  | 支持的记录数据子项，支持多个值，参考下表  <br /> |

| 数据项类型 | 记录数据类型 | 记录数据子项类型                                               |
| ---------- | -------------- | ------------------------------------------------------------ |
| 无         | 0           |                                                              |                                                           |
| 症状       | 1           | 1：眩晕<br/>2：呕吐<br/>3：失眠<br/>4：头痛<br/>5：痤疮<br/>6：掉发<br/>7：恶心<br/>8：记忆力衰退<br/>9：腹部绞痛<br/>10：腹泻<br/>11：腹胀<br/>12：盆腔疼痛<br/>13：发冷<br/>14：浮肿<br/>15：皮肤干燥<br/>16：食欲变化<br/>17：乳房疼痛<br/>18：腰酸背痛<br/>19：心情变化<br/>20：夜间盗汗<br/>21：膀胱失禁<br/>22：便秘<br/>23：潮热<br/> | 
| 点滴出血   | 2           | 0：不出血，1：出血                                               | 

`示例：`

```json
{
  "version": 0,
  "operate":1,
  "last_change_time" : 0,
  "all_items_num": 1,
  "data_items": [
    {
      "year": 2023,
      "mon": 8,
      "day": 1,
      "items_num": 1,
      "last_change_time":0,
      "change_type":14,
      "items" :
      [
        {
          "data_type" : 1,
          "items_len" : 1,
          "data_items":[1]
        },
        {
          "data_type" : 2,
          "items_len" : 1,
          "data_items":[1]
        }
      ],
    }
  ],
  "configure_items_num": 2,
  "configure_items" :
  [
    {
      "data_type" : 1,
      "data_value":[1,2,3,4,5,6,7,8,9]
    },
    {
      "data_type" : 2,
      "data_value":[1]
    }
  ]
}
```

