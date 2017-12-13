---
layout: docsMember
permalink: docs/Variables/ToArrayFromTextFile/

categories:
    - Методы расширения переменных

title:          ToArrayFromTextFile
member:
    type:       method
    name:       ToArrayFromTextFile()
    summary:    'Считывает содержимое файла в массив.'
    returns:    'Массив строковых значений.'
    params:

---

```csharp
project.Variables["temp"].Value = @"C:\temp.txt";
string[] value = project.Variables["temp"].ToArrayFromTextFile();
project.SendInfoToLog(value.Length.ToString(), true);
```
