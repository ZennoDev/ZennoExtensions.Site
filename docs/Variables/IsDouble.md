---
layout: docsMember
permalink: /docs/Variables/IsDouble

categories:
    - Методы расширения переменных

title:          IsDouble
member:
    type:       method
    name:       IsDouble()
    summary:    'Проверяет является ли значение переменной вещественным числом.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "125,23";
if (project.Variables["temp"].IsDouble())
{
    project.SendInfoToLog("Значение переменной temp является вещественным числом.", true);     
}
```
