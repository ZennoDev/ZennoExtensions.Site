---
layout: docsMember
permalink: docs/Variables/ThrowIfNotRange/

categories:
    - Методы расширения переменных

title:          ThrowIfNotRange
member:
    type:       method
    name:       ThrowIfNotRange(string exceptionMessage, char separator)
    summary:    'Бросает исключение, если значение переменной не является диапазоном.'
    returns:    'Тот же экземпляр ILocalVariable для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'
        - name:  separator
          value: 'Разделитель'

---

```csharp
project.Variables["temp"].Value = "1 — 23";
project.Variables["temp"].ThrowIfNotRange("Значение переменной temp не является диапазоном значений.");
```
