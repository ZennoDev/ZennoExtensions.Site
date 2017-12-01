---
layout: docsMember
permalink: docs/Variables/Spintax/

categories:
    - Методы расширения переменных

title:          Spintax
member:
    type:       method
    name:       Spintax()
    summary:    'Применяет Spintax к содержимому переменной.'
    returns:    'Строка'
    params:

---

```csharp
project.Variables["temp"].Value = "{One | Two | Three}";
string value = project.Variables["temp"].Spintax();
project.SendInfoToLog(value, true);
```
