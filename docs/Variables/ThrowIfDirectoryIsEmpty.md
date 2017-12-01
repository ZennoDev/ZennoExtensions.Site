---
layout: docsMember
permalink: docs/Variables/ThrowIfDirectoryIsEmpty/

categories:
    - Методы расширения переменных

title:          ThrowIfDirectoryIsEmpty
member:
    type:       method
    name:       ThrowIfDirectoryIsEmpty(System.String exceptionMessage)
    summary:    'Бросает исключение, если директория пуста.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "C:\YourDirectoryPath\";
project.Variables["temp"].ThrowIfDirectoryIsEmpty("Директория C:\YourDirectoryPath\ пуста."); //Выбросит исключение, если директория не содержит файлов.
```
