### V3获取固件的歌曲名和文件夹


功能表:getSupportGetBleMusicInfoVerV3

**Flutter示例：**

```dart
/// 获取固件的歌曲名和文件夹事件号
getBleMusicInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_ble_music_info),

/// 获取固件的歌曲名和文件夹
libManager.send(evt: CmdEvtType.getBleMusicInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| version       | int      | 协议库版本号                                                 |
| all_memory    | int      | 固件sdk卡信息<br />总的空间                                  |
| useful_memory | int      | 固件sdk卡信息<br />可用的空间                                |
| used_memory   | int      | 固件sdk卡信息<br />当前使用的空间 单位字节                   |
| folder_num    | int      | (歌单)文件夹详情个数                                         |
| music_num     | int      | 音乐详情个数                                                 |
| folder_items  | 集合     | (歌单)文件夹详情<br />folder_id & music_num & folder_name & music_index的集合 |
| music_items   | 集合     | 音乐详情<br />music_id & music_memory & music_name & singer_name的集合 |

| 字段名      | 字段类型 | 字段说明                                         |
| ----------- | -------- | ------------------------------------------------ |
| folder_id   | int      | 歌单(文件夹) id 1~10                             |
| music_num   | int      | 歌单中的歌曲数目 最多100个                       |
| folder_name | char []  | 歌单(文件夹)名称 最大20个字节                    |
| music_index | int []   | 歌单中对应歌曲的id，按照添加的先后顺序，依次排列 |

| 字段名       | 字段类型 | 字段说明            |
| ------------ | -------- | ------------------- |
| music_id     | int      | 音乐id 从1开始      |
| music_memory | int      | 音乐占用的空间      |
| music_name   | char []  | 音乐名 最大45个字节 |
| singer_name  | char []  | 歌手名 最大30个字节 |

`示例：`

```c
{
    "version":0,
    "icon_width":200,
    "icon_height":120,
    "format":133,
    "block_size":1024,
    "pack_name_num":0,
    "package_num":0,
    "items":null
}
```
