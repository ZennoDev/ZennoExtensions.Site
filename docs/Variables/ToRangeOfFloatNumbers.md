---
layout: docsMember
permalink: docs/Variables/ToRangeOfFloatNumbers/

categories:
    - Методы расширения переменных

title:          ToRangeOfFloatNumbers
member:
    type:       method
    name:       ToRangeOfFloatNumbers(char separator)
    summary:    'Конвертирует строковое значение переменной в диапазон вещественных чисел.'
    returns:    'Диапазон вещественных чисел.'
    params:
        - name:  separator
          value: 'Разделитель. По умолчанию "-".'

---

```csharp
project.Variables["temp"].Value = "100.3 — 200.11";
var range = project.Variables["temp"].ToRangeOfFloatNumbers('—');
project.SendInfoToLog("Диапазон вещественных чисел от " + range.From.ToString() + " до " + range.To.ToString(), true);
```
