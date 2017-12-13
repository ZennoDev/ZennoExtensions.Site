---
layout: docsMember
permalink: docs/Variables/ToStringFromTextFile/

categories:
    - Методы расширения переменных

title:          ToStringFromTextFile
member:
    type:       method
    name:       ToStringFromTextFile()
    summary:    'Считывает содержимое файла в строку.'
    returns:    'Содержимое файла.'
    params:

---

```csharp
project.Variables["temp"].Value = @"C:\temp.txt";
string value = project.Variables["temp"].ToStringFromTextFile();
project.SendInfoToLog(value, true);
```
