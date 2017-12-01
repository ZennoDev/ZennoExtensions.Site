---
layout: docsMember
permalink: docs/Variables/ToArray/

categories:
    - Методы расширения переменных

title:          ToArray
member:
    type:       method
    name:       ToArray(System.Char separator)
    summary:    'Разбивает строковое значение переменной на массив значений.'
    returns:    'Массив строковых значений'
    params:
        - name:  separator
          value: 'Разделитель'

---

```csharp
project.Variables["temp"].Value = "1;2;3;4;5;6;7;8";
string[] value = project.Variables["temp"].ToArray(';');
project.SendInfoToLog(value.Length.ToString(), true);
```
