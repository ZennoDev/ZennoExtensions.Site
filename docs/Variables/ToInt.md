---
layout: docsMember
permalink: /docs/Variables/ToInt

categories:
    - Методы расширения переменных

title:          ToInt
member:
    type:       method
    name:       ToInt()
    summary:    'Конвертирует строковое значение переменной в Int32.'
    returns:    'Целое число'
    params:

---

```csharp
project.Variables["temp"].Value = "123";
int value = project.Variables["temp"].ToInt();
project.SendInfoToLog(value.ToString(), true);
```
