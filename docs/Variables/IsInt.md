---
layout: docsMember
permalink: docs/Variables/IsInt/

categories:
    - Методы расширения переменных

title:          IsInt
member:
    type:       method
    name:       IsInt()
    summary:    'Проверяет является ли значение переменной целым числом.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "125";
if (project.Variables["temp"].IsInt())
{
    project.SendInfoToLog("Значение переменной temp является целым числом.", true);     
}
```
