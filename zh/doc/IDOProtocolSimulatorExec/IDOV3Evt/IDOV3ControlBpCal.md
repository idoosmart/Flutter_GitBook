### V3操作血压校准控制

功能表:setSupportV3Bp


**Flutter示例：**

```dart
/// v3血压校准控制
setBpCalControlV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_bp_cal_control),

/// v3血压校准控制
libManager.send(evt: CmdEvtType.setBpCalControlV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| operate   | int      | 0：无效<br />1：开始设置血压校准<br />2：停止设置血压校准<br />3：获取特性向量信息 |
| file_path | char []  | 获取固件血压校准的原始数据后保存到的文件路径<br />路径包含文件名(../../blood.txt)<br />operate=1时有效 |

`示例：`

```c
{
  "operate": 1,
  "file_path":"/sdcard/lx/blood.txt"
}
```

**App收到的json字段**：

| 字段名                | 字段类型 | 字段说明                                                     |
| --------------------- | -------- | ------------------------------------------------------------ |
| error_code            | int      | 错误码 0成功，非0失败                                        |
| operate               | int      | 操作 <br />0：无效<br />1：开始设置血压校准<br />2：停止设置血压校准 <br />3：获取特性向量 |
| sbp_ppg_feature_num   | int      | 高压ppg特性向量组数<br />operate=3有效                       |
| dbp_ppg_feature_num   | int      | 低压ppg特性向量组数<br />operate=3有效                       |
| sbp_ppg_feature_items | int []   | 高压ppg特性向量数组<br />operate=3有效                       |
| dbp_ppg_feature_items | int []   | 低压ppg特性向量数组<br />operate=3有效                       |

`示例：`

```c
{
  "error_code": 0,
  "operate":1,
  "sbp_ppg_feature_num":0,
  "dbp_ppg_feature_num":0,
  "dbp_ppg_feature_num":null;
  "dbp_ppg_feature_num":null;
}
```

