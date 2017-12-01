---
layout: docsMember
permalink: docs/Variables/IsEmpty/

categories:
    - Методы расширения переменных

title:          IsEmpty
member:
    type:       method
    name:       IsEmpty()
    summary:    'Проверяет указано ли значение переменной.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "";
if (project.Variables["temp"].IsEmpty())
{
    project.SendInfoToLog("Переменная temp не содержит значения.", true);     
}
```
