---
layout: docsMember
permalink: docs/Variables/ThrowIfNotArray/

categories:
    - Методы расширения переменных

title:          ThrowIfNotArray
member:
    type:       method
    name:       ThrowIfNotArray(string exceptionMessage, char separator)
    summary:    'Бросает исключение, если значение переменной не является массивом данных.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'
        - name:  separator
          value: 'Разделитель'

---

```csharp
project.Variables["temp"].Value = "1,2,3,4";
project.Variables["temp"].ThrowIfNotArray();
project.SendInfoToLog("Переменная temp содержит массив значений.", true); 

project.Variables["temp"].Value = "123";
project.Variables["temp"].ThrowIfNotArray("Значение переменной temp не является массивом.");  //Выбросит исключение
```
