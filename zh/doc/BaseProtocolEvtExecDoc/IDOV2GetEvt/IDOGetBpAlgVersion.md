### 获取血压算法三级版本号信息


功能表:setSupportV3Bp

**Flutter示例：**

```dart
  /// 获取血压算法三级版本号信息事件号
getBpAlgVersion(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_bp_alg_version),

/// 获取血压算法三级版本号信息
libManager.send(evt: CmdEvtType.getBpAlgVersion, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                                     | 字段类型 | 字段说明                 |
| ------------------------------------------ | -------- | ------------------------ |
| 三级版本号拼接：version1.version2.version3 |          |                          |
| bp_version_1                                 | int      | 固件血压算法版本version1 |
| bp_version_2                                 | int      | 固件血压算法版本version2 |
| bp_version_3                                 | int      | 固件血压算法版本version3 |

`示例：`

```c
{
    "bp_version_1":0,
    "bp_version_2":0,
    "bp_version_3":6
}
```
