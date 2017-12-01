---
layout: docsMember
permalink: /docs/Variables/ThrowIfEmpty

categories:
    - Методы расширения переменных

title:          ThrowIfEmpty
member:
    type:       method
    name:       ThrowIfEmpty(System.String exceptionMessage)
    summary:    'Бросает исключение, если переменная пустая.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
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
