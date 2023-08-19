### V3操作小程序信息


**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| verison           | int      | 协议库版本号                                                 |
| operate           | int      | 0:无效 1:启动小程序 2:删除小程序 3:获取已安装的小程序列表    |
| mini_program_name | char []   | 小程序名称 <br />operate=0/operate=3无效,获取操作不需要下发名称<br />最大30个字节 |

`示例：`

```c
{
  "verison":0,
  "operate":1,
  "mini_program_name":"粤康码"
}
```

**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| version          | int      | 协议库版本号                                                 |
| operate          | int      | 0:无效 1:启动小程序 2:删除小程序 3:获取已安装的小程序列表    |
| error_code       | int      | 0:成功 非0失败                                               |
| mini_program_num | int      | operate=3有效<br />小程序个数 最多50个                       |
| residual_space   | int      | 剩余空间                                                     |
| total_space      | int      | 总空间                                                       |
| info_item        | 集合     | 小程序列表<br />mini_program_name & mini_program_size &mini_program_version的集合<br />operate=3有效 |

| 字段名               | 字段类型 | 字段说明                  |
| -------------------- | -------- | ------------------------- |
| mini_program_name    | char []  | 小程序名称 最大值30个字节 |
| mini_program_size    | int      | 小程序大小                |
| mini_program_version | int      | 小程序版本号              |

`示例：`

```c
{
  "version":0,
    "operate":1,
    "error_code":0,
    "mini_program_num":0,
    "residual_space": 0,
    "total_space":0,
    "info_item":null
}
```
