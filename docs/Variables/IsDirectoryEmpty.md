---
layout: docsMember
permalink: docs/Variables/IsDirectoryEmpty/

categories:
    - Методы расширения переменных

title:          IsDirectoryEmpty
member:
    type:       method
    name:       IsDirectoryEmpty()
    summary:    'Проверяет есть ли файлы в директории.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "C:\TestDirectoryPath\";
if (project.Variables["temp"].IsDirectoryEmpty())
{
    project.SendInfoToLog("Директория не содерижт файлов.", true);     
}
```
