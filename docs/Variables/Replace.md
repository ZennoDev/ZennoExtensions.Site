---
layout: docsMember
permalink: docs/Variables/Replace/

categories:
    - Методы расширения переменных

title:          Replace
member:
    type:       method
    name:       Replace(System.String oldValue,System.String newValue)
    summary:    'Заменяет содержимое переменной: все вхождения заданной строки заменены другой заданной строкой.'
    returns:    'Экземпляр переменной.'
    params:
        - name:  oldValue
          value: 'Строка, которую требуется заменить.'
        - name:  newValue
          value: 'Строка для замены всех вхождений oldValue.'

---

```csharp
project.Variables["temp"].Value = @"Удалить";
string value = project.Variables["temp"].Replace("Удалить", "Delete");
project.SendInfoToLog(value, true); // Delete
```
