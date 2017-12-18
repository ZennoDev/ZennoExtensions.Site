---
layout: docsMember
permalink: docs/Variables/IsDate/

categories:
    - Методы расширения переменных

title:          IsDate
member:
    type:       method
    name:       IsDate()
    summary:    'Проверяет является ли значение переменной датой.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "11.11.2011";
if (project.Variables["temp"].IsDate())
{
    project.SendInfoToLog("Значение переменной temp является датой.", true);     
}
```
