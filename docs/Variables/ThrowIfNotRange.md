---
layout: docsMember
permalink: docs/Variables/ThrowIfNotRange/

categories:
    - Методы расширения переменных

title:          ThrowIfNotRange
member:
    type:       method
    name:       ThrowIfNotRange(System.String separator,System.Char exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является диапазоном.'
    returns:    'Тот же экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.ILocalVariable" /> для Fluent Interface'
    params:
        - name:  separator
          value: 'Разделитель'
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "1 — 23";
project.Variables["temp"].ThrowIfNotRange("Значение переменной temp не является диапазоном значений.");
```
