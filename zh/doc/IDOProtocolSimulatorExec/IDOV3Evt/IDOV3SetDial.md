### V3设置表盘

功能表：getMultiDial 【v3WatchDailSetAddSize】

**Flutter示例：**

```dart
/// 设置表盘事件号
setWatchFaceData(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_set_watch_face_data),

/// 设置表盘
libManager.send(evt: CmdEvtType.setWatchFaceData, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| operate         | int      | 操作 <br />0  查询正在使用表盘<br />1 设置表盘<br />2 删除表盘<br />3 动态申请空间设置对应的空间大小 |
| file_name       | char []   | 表盘名，最大值29个字节                                     |
| watch_file_size | int      | 未压缩的文件长度<br />固件开启功能表`v3WatchDailSetAddSize`后app需要下发该字段<br />表盘传输前，固件需要开辟对应的空间保存，需要把未压缩的文件长度传输过去 |

`示例：`

```c
{
    "operate":0,
    "file_name":"",
    "watch_file_size":0
}
```
**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| err_code   | int      | 错误码，0成功，非0错误                                       |
| operate    | int      | 操作 <br />0  查询正在使用表盘<br />1 设置表盘<br />2 删除表盘<br />3 动态申请空间设置对应的空间大小 |
| file_name  | char []   | 表盘名，最大值29个字节                                      |
| file_count | int      | 文件的个数<br />需要固件开启功能表`v3WatchDailSetAddSize`<br />如果operate!=3,这个数据就是1和以前保存一样<br />如果operate =3,动态申请空间设置对应的空间大小，这个对应的就是一个删除的文件名列<br />如果`v3WatchDailSetAddSize`未开启,该字段默认返回1 |

`示例：`

```c
{
    "err_code":0,
    "operate":0,
    "file_name":"w256.iwf",
    "file_count":0
}
```