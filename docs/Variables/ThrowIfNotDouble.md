---
layout: docsMember
permalink: docs/Variables/ThrowIfNotDouble/

categories:
    - Методы расширения переменных

title:          ThrowIfNotDouble
member:
    type:       method
    name:       ThrowIfNotDouble(string exceptionMessage)
    summary:    'Бросает исключение, если значение переменной не является вещественным числом.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
project.Variables["temp"].Value = "1.23";
project.Variables["temp"].ThrowIfNotDouble();
project.SendInfoToLog("Переменная temp содержит вещественное значение.", true); 

project.Variables["temp"].Value = "not double";
project.Variables["temp"].ThrowIfNotDouble("Значение переменной temp не является вещественным числом.");  //Выбросит исключение
```
