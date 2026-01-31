### Daily Menstrual Recording

Function: setHistoryMenstrual [supportPhysiologicalRecord]

**Flutter Example:**

```dart
/// Daily Menstrual Recording Event Number
setMenstruationRecord(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_v3_physiological_record),

/// Daily Menstrual Recording Data Delivery
libManager.send(evt: CmdEvtType.setMenstruationRecord, json: jsonEncode(json));
```

**JSON Fields Delivered by the App**:

| Field Name | Field Type | Field Description |
|-----------------------------------|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| version | int | Protocol Library Version Number<br />Default: 0 |
| operate | int | Operation type <br/>0: Invalid <br/>1: Full setting <br/>2: Query daily physiological record items <br/>3: Query daily physiological record data <br/>4: Modify <br/>5: Add <br/>6: Delete <br/>7: Get firmware modification items |
| last_change_time | long | The time of the last modification. All operations (modify, add, and delete) must update the time. Timestamp, unit: seconds |
| data_items | Collection | Daily physiological record data list. <br/>Collection of `year` & `mon` & `day` & menstrual_day` & `cycle_day` <br/>`ovulation_interval_day` & `ovulation_before_day` & `ovulation_after_day` |
| all_items_num | int | Number of `data_items` in the daily physiological record data list |
| Field name | Field type | Field description |
|------------------------|------|------------------------------------------------------------------------------------------------------------|
| year | int | Recorded year |
| mon | int | Recorded month |
| day | int | Recorded day |
| last_change_time | long | Time of the last modification. All operations (modify, add, and delete) must update the time. Timestamp, unit: seconds |
| change_type | int | Modification type, <font color='#ff0000'>Get modification item valid (operate=7)</font> <br/> 0: Invalid <br/> 1: Add <br/> 2: Modify <br/> 3: Delete, the watch deleted the data item |
| items_num | int | List of various data types recorded daily (items) |
| items | Collection | List of various data types recorded daily (a collection of `data_type`, `items_len`, and `data_items`) |
| Field name | Field type | Field description |
|-----------|------|------------------------------------------------------------|
| data_type | int | Record data type<br/> 0x01: Symptom<br/> 0x02: Spotting |
| data_items | Collection | Record data sub-items. Multiple values are supported. See the table below.<br /> |
| items_len | Collection | Number of record data sub-items<br /> |
| Data item type | Record data type | Record data sub-item type |
| ---------- | -------------- | ------------------------------------------------------------ |
| None | 0 | | |
| Symptom | 1 | 1: Dizziness<br/>2: Vomiting<br/>3: Insomnia<br/>4: Headache<br/>5: Acne<br/>6: Hair loss<br/>7: Nausea<br/>8: Memory loss<br/>9: Abdominal cramps<br/>10: Diarrhea<br/>11: Bloating<br/>12: Pelvic pain<br/>13: Chills<br/>14: Edema<br/>15: Dry skin<br/>16: Appetite changes<br/>17: Breast pain<br/>18: Back pain<br/>19: Mood changes<br/>20: Night sweats<br/>21: Bladder incontinence<br/>22: Constipation<br/>23: Hot flashes<br/> |
| Spotting | 2 | 0: No bleeding, 1: Bleeding |


`Example:`

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
**JSON fields received by the app**:

| Field name | Field type | Field description |
|-----------------------------------|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| version | int | Protocol library version number<br />Default: 0 |
| operate | int | Operation type <br /> 0: Invalid <br /> 1: Full settings <br /> 2: Query daily physiological record items <br /> 3: Query daily physiological record data <br /> 4: Modify <br /> 5: Add <br /> 6: Delete <br /> 7: Get firmware modification items |
| last_change_time | long | Time of last modification. Operations such as modification, addition, and deletion must update the time (timestamp, unit: seconds). |
| data_items | Collection | Daily physiological record data list<br /> Collection of `year` & `mon` & `day` & `menstrual_day` & `cycle_day` <br /> `ovulation_interval_day` & `ovulation_before_day` & `ovulation_after_day` |
| all_items_num | int | Number of `data_items` in the daily menstrual data list |

| Field Name | Field Type | Field Description |
|------------------------|------|--------------------------------------------------------------------------------------------|
| year | int | Recorded year |
| mon | int | Recorded month |
| day | int | Recorded day |
| last_change_time | long | Time of the last modification. All operations (modify, add, and delete) must update the time. Timestamp, unit: seconds |
| change_type | int | Modification type, <font color='#ff0000'>Get modification item valid (operate=7)</font> <br/> 0: Invalid <br/> 1: Add <br/> 2: Modify <br/> 3: Delete, the watch deleted the data item |
| items_num | int | Number of `items` in the daily data list of various types |
| items | Collection | List of various types of data recorded daily. Collection of `data_type`, `items_len`, and `data_items` |
| configure_items_num | int | Supported record types and the number of `configure_items` data items |
| configure_items | Collection | Supported record types and data items. Collection of `data_type` and `data_value` |

| Field Name | Field Type | Field Description |
|-----------|------------------------------------------------------------|
| data_type | int | Record data type. 0x01: Symptoms. 0x02: Spotting. |
| data_items | Collection | Record data items. Multiple values are supported. See the table below. <br /> |
| items_len | Collection | Record the number of data items. <br /> |

| Field Name | Field Type | Field Description |
|-----------|------|------------------------------------------------------------|
| data_type | int | Supported record data types<br/> 0x01: Symptom<br/> 0x02: Spotting |
| data_value | Collection | Supported record data sub-items. Multiple values are supported. See the table below. <br /> |

| Data item type | Record data type | Record data sub-item type |
| ---------- | -------------- | ------------------------------------------------------------ |
| None | 0 | | |
| Symptom | 1 | 1: Dizziness<br/>2: Vomiting<br/>3: Insomnia<br/>4: Headache<br/>5: Acne<br/>6: Hair loss<br/>7: Nausea<br/>8: Memory loss<br/>9: Abdominal cramps<br/>10: Diarrhea<br/>11: Bloating<br/>12: Pelvic pain<br/>13: Chills<br/>14: Edema<br/>15: Dry skin<br/>16: Appetite changes<br/>17: Breast pain<br/>18: Back pain<br/>19: Mood changes<br/>20: Night sweats<br/>21: Bladder incontinence<br/>22: Constipation<br/>23: Hot flashes<br/> |
| Spotting | 2 | 0: No bleeding, 1: Bleeding |

`Example:`

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

