---
layout: docsMember
permalink: docs/Variables/IsDirectoryExists/

categories:
    - Методы расширения переменных

title:          IsDirectoryExists
member:
    type:       method
    name:       IsDirectoryExists()
    summary:    'Проверяет существует ли директория по указанному пути.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "C:\TestDirectoryPath\";
if (!project.Variables["temp"].IsDirectoryExists())
{
    project.SendInfoToLog("Директория по указанному пути не существует.", true);     
}
```
