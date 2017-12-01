---
layout: docsMember
permalink: docs/Variables/ThrowIfNotArray/

categories:
    - Методы расширения переменных

title:          ThrowIfNotArray
member:
    type:       method
    name:       ThrowIfNotArray(System.String separator,System.Char exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является массивом данных.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  separator
          value: 'Разделитель'
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "1,2,3,4";
project.Variables["temp"].ThrowIfNotArray();
project.SendInfoToLog("Переменная temp содержит массив значений.", true); 

project.Variables["temp"].Value = "123";
project.Variables["temp"].ThrowIfNotArray("Значение переменной temp не является массивом.");  //Выбросит исключение
```
