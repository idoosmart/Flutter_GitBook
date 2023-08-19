### V3语音回复文本


功能表:getSportsTypeV3

**Flutter示例：**

```dart
/// v3语音回复文本事件号
setVoiceReplyTxtV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_voice_reply_txt),

/// v3语音回复文本
libManager.send(evt: CmdEvtType.setVoiceReplyTxtV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名           | 字段类型 | 字段说明                                |
| ---------------- | -------- | --------------------------------------- |
| version          | int      | 协议版本号 2                         |
| flag_is_continue | int      | 继续录音的标志<br />0停止录音 1继续录音 |
| title            | char []    | 标题数据<br />最大值32字节              |
| text_content     | char []    | 信息数据<br />最大值512字节             |

`示例：`

```c
{
    "version":0,
    "flag_is_continue":1,
    "title":"title",
    "text_content":"content"
}
```
**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明     |
| ---------- | -------- | ------------ |
| is_success | int      | 1成功  0失败 |

`示例：`

```c
{
    "is_success":1
}
```

