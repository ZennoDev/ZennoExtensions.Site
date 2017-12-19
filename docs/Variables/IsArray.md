---
layout: docsMember
permalink: docs/Variables/IsArray/

categories:
    - Методы расширения переменных

title:          IsArray
member:
    type:       method
    name:       IsArray(char separator)
    summary:    'Проверяет является ли строка массивом данных.'
    returns:    'true / false'
    params:
        - name:  separator
          value: 'Разделитель.'

---

```csharp
project.Variables["temp"].Value = "1;3;4;77;5;3";
if (project.Variables["temp"].IsArray(';'))
{
    project.SendInfoToLog("Значение переменной temp является массивом значений.", true);     
}
```
