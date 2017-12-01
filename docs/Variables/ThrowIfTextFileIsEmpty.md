---
layout: docsMember
permalink: /docs/Variables/ThrowIfTextFileIsEmpty

categories:
    - Методы расширения переменных

title:          ThrowIfTextFileIsEmpty
member:
    type:       method
    name:       ThrowIfTextFileIsEmpty(System.String exceptionMessage)
    summary:    'Бросает исключение, если файл пуст.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "C:\onetwothree.txt";
project.Variables["temp"].ThrowIfTextFileIsEmpty("Файл onetwothree.txt пуст."); //Выбросит исключение, если файла не существует.
```
