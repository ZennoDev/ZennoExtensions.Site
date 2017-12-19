---
layout: docsMember
permalink: docs/Int32/UnixTimeToDateTime/

categories:
    - Методы расширения Int32

title:          UnixTimeToDateTime
member:
    type:       method
    name:       UnixTimeToDateTime()
    summary:    'Конвертирует число представляющее UnixTime в соответствующую дату в формате DateTime.'
    returns:    'Структура DateTime.'
    params:

---

```csharp
int unixTime = 1513120110;
DateTime date = unixTime.UnixTimeToDateTime(); // 12.12.2017
```