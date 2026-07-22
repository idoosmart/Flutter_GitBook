### 获取单位


功能表:getSupportGetUnit

**Flutter示例：**

```dart
/// 获取单位
getUnit(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_unit),

/// 获取单位
libManager.send(evt: CmdEvtType.getUnit, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| dist_unit      | int      | 公英制单位设置 <br />-1:无效 <br />1:km(公制) <br />2:mi(英制) |
| temp           | int      | 温度单位设置 <br />-1:无效 <br />1:摄氏度 <br />2:华氏度     |
| swim_pool_unit | int      | 泳池单位设置<br />-1:无效 <br />1:默认米 <br />2:码          |
| language       | int      | 语言<br />-1:无效<br />参考`语言code`表格                    |

**`语言code列表`**

| 代码 | 语言         | 功能表id                    |
| ---- | ------------ | --------------------------- |
| -1   | 无效         | -                           |
| 1    | 中文         | languageCh                  |
| 2    | 英文         | languageEnglish             |
| 3    | 法语         | languageFrench              |
| 4    | 德语         | languageGerman              |
| 5    | 意大利语     | languageItalian             |
| 6    | 西班牙语     | languageSpanish             |
| 7    | 日语         | languageJapanese            |
| 8    | 波兰语       | languagePolish              |
| 9    | 捷克语       | languageCzech               |
| 10   | 罗马尼亚     | languageRomanian            |
| 11   | 立陶宛语     | languageLithuanian          |
| 12   | 荷兰语       | languageDutch               |
| 13   | 斯洛文尼亚语 | languageSlovenian           |
| 14   | 匈牙利语     | languageHungarian           |
| 15   | 俄罗斯语     | languageRussian             |
| 16   | 乌克兰语     | languageUkrainian           |
| 17   | 斯洛伐克语   | languageSlovak              |
| 18   | 丹麦语       | languageDanish              |
| 19   | 克罗地亚语   | languageCroatian            |
| 20   | 印尼语       | languageIndonesian          |
| 21   | 韩语         | languageKorean              |
| 22   | 印地语       | languageHindi               |
| 23   | 葡萄牙语     | languagePortuguese          |
| 24   | 土耳其语     | languageTurkish             |
| 25   | 泰国语       | languageThai                |
| 26   | 越南语       | languageVietnamese          |
| 27   | 缅甸语       | languageBurmese             |
| 28   | 菲律宾语     | languageFilipino            |
| 29   | 繁体中文     | languageTraditionalChinese  |
| 30   | 希腊语       | languageGreek               |
| 31   | 阿拉伯语     | languageArabic              |
| 32   | 瑞典语       | languageSweden              |
| 33   | 芬兰语       | languageFinland             |
| 34   | 波斯语       | languagePersia              |
| 35   | 挪威语       | languageNorwegian           |
| 36   | 马来语       | languageMalay               |
| 37   | 巴西葡语     | languageBrazilianPortuguese |
| 38   | 孟加拉语     | languageBengali             |
| 39   | 高棉语       | languageKhmer               |

`获取单位示例：`

```json
{
  "dist_unit" :1,
  "temp" :1,
  "swim_pool_unit" :1,
  "language" : 1
}
```

