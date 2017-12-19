---
layout: docsMember
permalink: docs/Variables/ToRangeOfNumbers/

categories:
    - Методы расширения переменных

title:          ToRangeOfNumbers
member:
    type:       method
    name:       ToRangeOfNumbers(char separator)
    summary:    'Конвертирует строковое значение переменной в диапазон целых чисел.'
    returns:    'Диапазон целых чисел.'
    params:
        - name:  separator
          value: 'Разделитель. По умолчанию "-".'

---

```csharp
project.Variables["temp"].Value = "100 — 200";
var range = project.Variables["temp"].ToRangeOfNumbers('—');
project.SendInfoToLog("Диапазон целых чисел от " + range.From.ToString() + " до " + range.To.ToString(), true);
```
