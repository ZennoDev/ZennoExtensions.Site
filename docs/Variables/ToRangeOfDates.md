---
layout: docsMember
permalink: docs/Variables/ToRangeOfDates/

categories:
    - Методы расширения переменных

title:          ToRangeOfDates
member:
    type:       method
    name:       ToRangeOfDates(System.Char separator)
    summary:    'Конвертирует строковое значение переменной в диапазон дат.'
    returns:    'Диапазон дат.'
    params:
        - name:  separator
          value: 'Разделитель. По умолчанию "-".'

---

```csharp
project.Variables["temp"].Value = "10.02.2016 — 22.12.2017";
var range = project.Variables["temp"].ToRangeOfDates('—');
project.SendInfoToLog("Диапазон дат от " + range.From.ToString() + " до " + range.To.ToString(), true);
```
