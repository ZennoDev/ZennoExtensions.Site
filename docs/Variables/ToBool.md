---
layout: docsMember
permalink: docs/Variables/ToBool/

categories:
    - Методы расширения переменных

title:          ToBool
member:
    type:       method
    name:       ToBool()
    summary:    'Конвертирует строковое значение переменной в Boolean.'
    returns:    'true / false'
    params:

---

```csharp
project.Variables["temp"].Value = "True";
bool value = project.Variables["temp"].ToBool();
project.SendInfoToLog(value.ToString(), true);
```
