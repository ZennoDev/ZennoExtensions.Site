---
layout: docsMember
permalink: docs/Variables/ThrowIfEmpty/

categories:
    - Методы расширения переменных

title:          ThrowIfEmpty
member:
    type:       method
    name:       ThrowIfEmpty(string exceptionMessage)
    summary:    'Бросает исключение, если переменная пустая.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "1";
project.Variables["temp"].ThrowIfEmpty();
project.SendInfoToLog("Переменная temp не пуста.", true);

project.Variables["temp"].Value = "";
project.Variables["temp"].ThrowIfEmpty("Переменная temp пуста.");  //Выбросит исключение
```
