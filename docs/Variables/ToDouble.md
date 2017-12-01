---
layout: docsMember
permalink: /docs/Variables/ToDouble

categories:
    - Методы расширения переменных

title:          ToDouble
member:
    type:       method
    name:       ToDouble()
    summary:    'Конвертирует строковое значение переменной в Double.'
    returns:    'Вещественное число'
    params:

---

```csharp
project.Variables["temp"].Value = "123,53";
double value = project.Variables["temp"].ToDouble();
project.SendInfoToLog(value.ToString(), true);
```
