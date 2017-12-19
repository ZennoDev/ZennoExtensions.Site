---
layout: docsMember
permalink: docs/Variables/ThrowIfTextFileIsEmpty/

categories:
    - Методы расширения переменных

title:          ThrowIfTextFileIsEmpty
member:
    type:       method
    name:       ThrowIfTextFileIsEmpty(string exceptionMessage)
    summary:    'Бросает исключение, если файл пуст.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "C:\onetwothree.txt";
project.Variables["temp"].ThrowIfTextFileIsEmpty("Файл onetwothree.txt пуст."); //Выбросит исключение, если файла не существует.
```
