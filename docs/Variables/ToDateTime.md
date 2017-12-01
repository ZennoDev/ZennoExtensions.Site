---
layout: docsMember
permalink: /docs/Variables/ToDateTime

categories:
    - Методы расширения переменных

title:          ToDateTime
member:
    type:       method
    name:       ToDateTime()
    summary:    'Конвертирует строковое значение переменной в DateTime.'
    returns:    'Структура DateTime'
    params:

---

```csharp
project.Variables["temp"].Value = "11.01.1999";
DateTime value = project.Variables["temp"].ToDateTime();
project.SendInfoToLog(value.ToString(), true);
```
