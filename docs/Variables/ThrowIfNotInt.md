---
layout: docsMember
permalink: docs/Variables/ThrowIfNotInt/

categories:
    - Методы расширения переменных

title:          ThrowIfNotInt
member:
    type:       method
    name:       ThrowIfNotInt(System.String exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является целым числом.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "123";
project.Variables["temp"].ThrowIfNotInt();
project.SendInfoToLog("Переменная temp содержит целое число.", true);  

project.Variables["temp"].Value = "not number";
project.Variables["temp"].ThrowIfNotInt("Значение переменной temp не является целым числом.");  //Выбросит исключение
```
