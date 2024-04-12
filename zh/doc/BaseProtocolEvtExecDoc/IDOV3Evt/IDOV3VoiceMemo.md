### V3语音备忘录


功能表:getSupportVoiceMemoOperate

**Flutter示例：**

```dart
/// 语音备忘录
  setVoiceMemo(
      evtBase: _VBusEvtBase.base_app_set,
      evtType: _VBusEvtType.vbus_evt_func_v3_voice_memo
  ),

/// 语音备忘录
libManager.send(evt: CmdEvtType.setVoiceMemo, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名      | 字段类型 | 字段说明                                                     |
| ----------- | -------- | ------------------------------------------------------------ |
| operate     | int      | 操作类型<br />0:无效 <br />1:查<br />2:改<br />3:请求设备上传指定序号的语音文件 |
| voice_num   | int      | 录音信息个数<br />操作`改&请求传输` 有效                     |
| voice_items | 集合     | 录音信息内容<br />操作`改&请求传输` 有效<br />`ecard_index` & `qrcode_char` & `qrcode_name` 的集合 |

| 字段名      | 字段类型 | 字段说明                        |
| ----------- | -------- | ------------------------------- |
| year        | int      | 录音时间 年                     |
| month       | int      | 录音时间 月                     |
| day         | int      | 录音时间 日                     |
| hour        | int      | 录音时间 时                     |
| minute      | int      | 录音时间 分                     |
| duration    | int      | 录音时长 <br />单位秒           |
| voice_index | int      | 语音序号 <br />从0开始          |
| name        | char []  | 语音名称 <br />默认长度29个字节 |



**App收到的json字段**：

| 字段名             | 字段类型 | 字段说明                                                     |
| ------------------ | -------- | ------------------------------------------------------------ |
| operate            | int      | 操作类型<br />0:无效 <br />1:查<br />2:改<br />3:请求设备上传指定序号的语音文件 |
| error_code         | int      | 错误码<br />0成功 1失败                                      |
| voice_num_max_len  | int      | 设备支持的最大语音个数<br />0默认是20条<br />非0的话以这个值作为语音可缓存的最大条数 |
| voice_name_max_len | int      | 设备支持的最大语音名称长度<br />0默认是29字节<br />非0的话以这个值作为语音名称最大长度 |
| voice_num          | int      | 录音信息个数<br />操作`改&请求传输` 有效                     |
| voice_items        | 集合     | 录音信息内容<br />操作`改&请求传输` 有效<br />`ecard_index` & `qrcode_char` & `qrcode_name` 的集合 |

| 字段名        | 字段类型 | 字段说明                                       |
| ------------- | -------- | ---------------------------------------------- |
| year          | int      | 录音时间 年                                    |
| month         | int      | 录音时间 月                                    |
| day           | int      | 录音时间 日                                    |
| hour          | int      | 录音时间 时                                    |
| minute        | int      | 录音时间 分                                    |
| duration      | int      | 录音时长 <br />单位秒                          |
| voice_index   | int      | 语音序号 <br />从0开始                         |
| is_voice_sync | int      | 语音是否同步标志 <br />0:未同步 <br />1:已同步 |
| name          | char []  | 语音名称 <br />默认长度29个字节                |

`设备回复增操作示例：`

```c
{
	//..
}
```
