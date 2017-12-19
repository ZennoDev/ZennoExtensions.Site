---
layout: docsMember
permalink: docs/DateTime/ToUnixTime/

categories:
    - Методы расширения DateTime

title:          ToUnixTime
member:
    type:       method
    name:       ToUnixTime()
    summary:    'Конвертирует дату в число в формате UnixTime.'
    returns:    'void'
    params:

---

```csharp
DateTime date = new DateTime(2017, 12, 12);
int unixTime = date.ToUnixTime();
```