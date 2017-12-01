---
layout: docsMember
permalink: docs/Variables/IsBool/

categories:
    - Методы расширения переменных

title:          IsBool
member:
    type:       method
    name:       IsBool()
    summary:    'Проверяет является ли значение переменной логическим значением.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "True";
if (project.Variables["temp"].IsBool())
{
    project.SendInfoToLog("Значение переменной temp является логическим.", true);     
}
```
