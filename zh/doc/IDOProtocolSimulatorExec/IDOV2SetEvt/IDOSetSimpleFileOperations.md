### 设置简单文件操作


**Flutter示例：**

```dart
/// 简单文件操作事件号
funcSimpleFileOpt(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_simple_file_operations),

/// 简单文件操作
libManager.send(evt: CmdEvtType.funcSimpleFileOpt, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| operate    | int      | 操作类型  <br />0 获取<br />1 覆盖<br />2 删除<br />3 复制 |
| index      | int      | 索引号                                                       |
| dest_index | int      | 目的索引,只用于复制,其他情况下无效                           |

`示例：`

```c
{
   "operate":0,
   "index":1,
   "dest_index":0
}
```



**App收到的json字段**：

| 字段名  | 字段类型 | 字段说明                                                |
| ------- | -------- | ------------------------------------------------------- |
| error   | int      | 错误码<br />0操作成功,其他值为错误                      |
| operate | int      | 操作类型  <br />0 获取<br />1 覆盖<br />1 删除 |
| index   | int      | 索引号                                                  |

`示例：`

```c
{
   "error":0,
   "operate":0,
   "index":1
}
```