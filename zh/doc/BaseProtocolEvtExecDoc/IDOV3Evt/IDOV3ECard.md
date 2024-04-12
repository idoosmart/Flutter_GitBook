### V3电子卡片


功能表:getSupportECardOperate

**Flutter示例：**

```dart
/// 电子卡片
  setEcardControl(
      evtBase: _VBusEvtBase.base_app_set,
      evtType: _VBusEvtType.vbus_evt_func_v3_ecard_control
  ),

/// 电子卡片
libManager.send(evt: CmdEvtType.setEcardControl, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| operate   | int      | 操作类型<br />0:无效 <br />1:增加<br />2:删除<br />3:查询<br />4:修改 |
| ecard_num | int      | 电子卡片个数 <br />操作`增 删 改`操作有效<br />最大设置1     |
| card      | 集合     | 电子卡片内容<br />操作`设置`起作用<br />`ecard_index` & `qrcode_char` & `qrcode_name` 的集合 |

| 字段名      | 字段类型 | 字段说明                        |
| ----------- | -------- | ------------------------------- |
| ecard_index | int      | 电子卡序号<br />从0开始         |
| qrcode_char | char []  | 二维码字符串<br />最大255个字节 |
| qrcode_name | char []  | 二维码名称<br />最大29个字节    |



**App收到的json字段**：

| 字段名              | 字段类型 | 字段说明                                                     |
| ------------------- | -------- | ------------------------------------------------------------ |
| operate             | int      | 操作类型<br />0:无效 <br />1:增加<br />2:删除<br />3:查询<br />4:修改 |
| error_code          | int      | 错误码<br />0成功 1失败                                      |
| qrcode_char_max_len | int      | 设备支持的最大二维码字符串最大长度<br />默认是255个字节<br />非0的话以这个值作为二维码字符串缓存的长度<br />操作`查询`起作用 |
| qrcode_name_max_len | int      | 设备支持的最大二维码名称最大长度<br />默认是29个字节<br />非0的话以这个值作为二维码名称缓存的长度<br />操作`查询`起作用 |
| card_max_len        | int      | 设备支持的电子卡片最大条数<br />默认是10条<br />非0的话以这个值作为电子卡片最大条数<br />操作`查询`起作用 |
| ecard_num           | int      | 电子卡片个数 <br />操作`查询`起作用                          |
| card                | 集合     | 电子卡片内容<br />操作`查询`起作用<br />`ecard_index` & `qrcode_char` & `qrcode_name` 的集合 |

| 字段名      | 字段类型 | 字段说明                        |
| ----------- | -------- | ------------------------------- |
| ecard_index | int      | 电子卡序号<br />从0开始         |
| qrcode_char | char []  | 二维码字符串<br />最大255个字节 |
| qrcode_name | char []  | 二维码名称<br />最大29个字节    |

`设备回复增操作示例：`

```c
{
	//..
}
```
