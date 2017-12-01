---
layout: docsMember
permalink: docs/Variables/IsFileExists/

categories:
    - Методы расширения переменных

title:          IsFileExists
member:
    type:       method
    name:       IsFileExists()
    summary:    'Проверяет существует ли файл по указанному пути.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "C:\accounts.txt";
if (!project.Variables["temp"].IsFileExists())
{
    project.SendInfoToLog("Указанный файл не существует.", true);     
}
```
