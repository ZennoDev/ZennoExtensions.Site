---
layout: docsMember
permalink: docs/Variables/ThrowIfNotDate/

categories:
    - Методы расширения переменных

title:          ThrowIfNotDate
member:
    type:       method
    name:       ThrowIfNotDate(string exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является датой.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "10.11.2017";
project.Variables["temp"].ThrowIfNotDate();
project.SendInfoToLog("Переменная temp содержит дату.", true); 

project.Variables["temp"].Value = "123";
project.Variables["temp"].ThrowIfNotDate("Значение переменной temp не является датой.");  //Выбросит исключение
```
