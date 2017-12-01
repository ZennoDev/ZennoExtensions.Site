---
layout: docsMember
permalink: /docs/Variables/ThrowIfNotBool

categories:
    - Методы расширения переменных

title:          ThrowIfNotBool
member:
    type:       method
    name:       ThrowIfNotBool(System.String exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является логическим значением.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "True";
project.Variables["temp"].ThrowIfNotBool();
project.SendInfoToLog("Переменная temp содержит логическое значение.", true);  

project.Variables["temp"].Value = "not boolean";
project.Variables["temp"].ThrowIfNotBool("Значение переменной temp не является логическим.");  //Выбросит исключение
```
