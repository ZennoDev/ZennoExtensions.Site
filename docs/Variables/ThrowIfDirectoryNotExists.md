---
layout: docsMember
permalink: docs/Variables/ThrowIfDirectoryNotExists/

categories:
    - Методы расширения переменных

title:          ThrowIfDirectoryNotExists
member:
    type:       method
    name:       ThrowIfDirectoryNotExists(string exceptionMessage)
    summary:    'Бросает исключение, если директория не существует по указанному пути.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "C:\YourDirectoryPath\";
project.Variables["temp"].ThrowIfDirectoryNotExists("Директория C:\YourDirectoryPath\ не существует"); //Выбросит исключение, если директория не существует.
```
