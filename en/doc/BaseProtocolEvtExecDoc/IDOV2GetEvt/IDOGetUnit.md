### Get units


Menu :getSupportGetUnit

**Flutter Example: **
```dart
/// Get the unit
getUnit(
evtBase: _VBusEvtBase.base_app_get,
evtType: _VBusEvtType.app_get_unit),

/// Get the unit
libManager.send(evt: CmdEvtType.getUnit, json: jsonEncode(json));
```



` json fields received by App:`

| Field Name | Field Type | Field Description |
| ------------ | -------- | ------------------------------------------------------------ |
| dist | int | <br />-1: invalid <br />1:km(metric) <br />2:mi(imperial) |
| temp | int | Temperature unit <br />-1: invalid <br />1: Celsius <br />2: Fahrenheit |
| swimPoolUnit | int | Pool unit Settings <br />-1: invalid <br />1: default meter <br />2: code |
| language | int | language <br />-1: invalid <br /> Refer to `Language code List` |

**`Language code List`**

| code | language | function table id |
| ---- | ------------ | --------------------------- |
| -1 | is not valid | - |
| 1 | Chinese | languageCh |
| 2 | English | languageEnglish |
| 3 | French | languageFrench |
| 4 | German | languageGerman |
| 5 | Italian | languageItalian |
| 6 | Spanish | languageSpanish |
| 7 | Japanese | languageJapanese |
| 8 | Polish | languagePolish |
| 9 | Czech | languageCzech |
| 10 | Romanian | languageRomanian |
| 11 | Lithuanian | languageLithuanian |
| 12 | Dutch | languageDutch |
| 13 | Slovenian | languageSlovenian |
| 14 | Hungarian | languageHungarian |
| 15 | Russian | languageRussian |
| 16 | Ukrainian | languageUkrainian |
| 17 | Slovak | languageSlovak |
| 18 | Danish | languageDanish |
| 19 | Croatian | languageCroatian |
| 20 | Indonesian | languageIndonesian |
| 21 | Korean | languageKorean |
| 22 | Hindi | languageHindi |
| 23 | Portuguese | languagePortuguese |
| 24 | Turkish | languageTurkish |
| 25 | Thai | languageThai |
| 26 | Vietnamese | languageVietnamese |
| 27 | Burmese | languageBurmese |
| 28 | Filipino | languageFilipino |
|29 | Traditional Chinese | languageTraditionalChinese |
| 30 | Greek | languageGreek |
| 31 | Arabic | languageArabic |
| 32 | Swedish | languageSweden |
| 33 | Finland | languageFinland |
| 34 | Persia | languagePersia |
| 35 | Norwegian | languageNorwegian |
| 36 | Malay | languageMalay |
|37 | Brazilian Portuguese | languageBrazilianPortuguese |
| 38 | Bengali | languageBengali |
| 39 | Khmer | languageKhmer |

`Get unit example:`

```json
{
  "dist" :1,
  "temp" :1,
  "swimPoolUnit" :1,
  "language" : 2
}