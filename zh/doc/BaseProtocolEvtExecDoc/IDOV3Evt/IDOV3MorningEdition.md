### V3晨报


功能表:getSupportMorningEdition

**Flutter示例：**

```dart
/// 晨报事件号
setMorningEdition(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.vbus_evt_func_v3_morning_edition
),

/// 设置晨报
libManager.send(evt: CmdEvtType.setMorningEdition, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| operate           | int      | 操作类型<br />0:无效 <br />1:查询<br />2:设置                |
| now_user_location | int      | 当前显示已添加的晨报索引<br />前面的对应的是已经添加的，这边位置后面是未添加的<br />操作`设置`起作用 |
| on_off            | int      | 晨报开关<br />0:关<br />1:开<br />操作`设置`起作用           |
| all_num           | int      | 晨报个数 <br />操作`设置`起作用                              |
| items             | int []   | 晨报内容<br />晨报类型列表<br />操作`设置`起作用<br />排序内容按`items`内的序号顺序进行排序 |



**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| operate           | int      | 操作类型<br />0:无效 <br />1:查询<br />2:设置                |
| error_code        | int      | 错误码<br />0成功 非0失败                                    |
| on_off            | int      | 晨报开关<br />0:关<br />1:开<br />-1:无效<br />操作`查询`起作用 |
| min_show_num      | int      | 最少显示个数<br />操作查询有效                               |
| max_show_num      | int      | 最大显示个数<br />查询起作用                                 |
| now_user_location | int      | 当前显示已添加的晨报索引<br />前面的对应的是已经添加的，这边位置后面是未添加的<br />操作`查询`起作用 |
| all_num           | int      | 晨报个数 <br />操作`查询`起作用                              |
| items             | int []   | 晨报内容<br />晨报类型列表<br />操作`查询`起作用<br />排序内容按`items`内的序号顺序进行排序 |

`设备回复增操作示例：`

```c
{
	//..
}
```
