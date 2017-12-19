---
layout: docsMember
permalink: docs/Variables/IsRange/

categories:
    - Методы расширения переменных

title:          IsRange
member:
    type:       method
    name:       IsRange(char separator)
    summary:    'Проверяет является ли значение переменной диапазоном чисел или дат.'
    returns:    'true / false'
    params:
        - name:  separator
          value: 'Разделитель. По умолчанию "-".'

---

```csharp
project.Variables["temp"].Value = "100 — 200";
if (project.Variables["temp"].IsRange('—'))
{
    project.SendInfoToLog("Значение переменной temp является диапазоном значений.", true);     
}
```
