### V3操作歌曲或者文件夹


**Flutter示例：**

```dart
/// 操作歌曲或者文件夹事件号
setMusicOperate(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_operate_ble_music),

/// 操作歌曲或者文件夹
libManager.send(evt: CmdEvtType.setMusicOperate, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| version        | int      | 协议库版本号                                                 |
| music_operate  | int      | 音乐操作<br />0：无效操作<br />1：删除音乐<br />2：增加音乐  |
| folder_operate | int      | 文件夹(歌单)操作<br />0：无效操作<br />1：删除文件夹<br />2：增加文件夹<br />3：修改歌单 <br />4：导入歌单 <br />5：音乐删除 |
| music_items    | 集合     | 音乐详情<br />music_id & music_memory & music_name & singer_name的集合 |
| folder_items   | 集合  | (歌单)文件夹详情<br />folder_id & music_num & folder_name & music_index的集合 |

| 字段名      | 字段类型 | 字段说明                                         |
| ----------- | -------- | ------------------------------------------------ |
| folder_id   | int      | 歌单(文件夹) id 1~10                             |
| music_num   | int      | 歌单中的歌曲数目 最多100个                       |
| folder_name | char []  | 歌单(文件夹)名称 最大19个字节                    |
| music_index | int []   | 歌单中对应歌曲的id，按照添加的先后顺序，依次排列 |

| 字段名       | 字段类型 | 字段说明            |
| ------------ | -------- | ------------------- |
| music_id     | int      | 音乐id 从1开始      |
| music_memory | int      | 音乐占用的空间      |
| music_name   | char []  | 音乐名 最大44个字节 |
| singer_name  | char []  | 歌手名 最大29个字节 |

`示例：`

```c
{
    "version":0,
    "music_operate":0,
    "folder_operate":2,
    "music_items":null,
    "folder_items":
    {
        "folder_id":1,
        "music_num":0,
        "folder_name":"music fold 1"
        "music_index":[]
    }
}
```

**App收到的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| operate_type | int      | 操作类型：<br />0：无效操作<br />1：删除音乐<br />2：增加音乐<br />3：删除文件夹<br />4：增加文件夹<br />5：修改歌单  <br />6：导入歌单<br />7：歌单中音乐删除 |
| version      | int      | 固件sdk卡信息<br />总的空间                                  |
| err_code     | int      | 0成功 非0失败                                                |
| music_id     | int      | 当操作为 2:增加音乐成功时返回音乐id  音乐id                  |

`示例：`

```c
{
    "operate_type":4,
    "version":0,
    "err_code":0,
    "music_id":0
}
```
