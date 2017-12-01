---
layout: docsMember
permalink: /docs/Variables/ThrowIfFileNotExists

categories:
    - Методы расширения переменных

title:          ThrowIfFileNotExists
member:
    type:       method
    name:       ThrowIfFileNotExists(System.String exceptionMessage)
    summary:    'Бросает исключение, если файл не существует по указанному пути.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "C:\onetwothree.txt";
project.Variables["temp"].ThrowIfFileNotExists("Файл onetwothree.txt не существует."); //Выбросит исключение, если файла не существует.
project.SendInfoToLog("Файл onetwothree.txt найден.", true);
```
