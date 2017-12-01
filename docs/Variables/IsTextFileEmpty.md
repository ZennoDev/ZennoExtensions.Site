---
layout: docsMember
permalink: /docs/Variables/IsTextFileEmpty

categories:
    - Методы расширения переменных

title:          IsTextFileEmpty
member:
    type:       method
    name:       IsTextFileEmpty()
    summary:    'Проверяет пуст ли текстовый файл.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "C:\accounts.txt";
if (project.Variables["temp"].IsTextFileEmpty())
{
    project.SendInfoToLog("Файл пуст.", true);     
}
```
