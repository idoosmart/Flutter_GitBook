### 设置停止寻找手机


功能表:setOverFindPhone

**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明       |
| ------ | -------- | -------------- |
| states | int      | 1: 结束寻找 |

`示例：`

```c
{
  "states":1
}
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明                     |
| ------ | -------- | ---------------------------- |
| status | int      | 成功：0  <br />失败：1 |

`示例：`

```c
{
  "status":0
}
```
