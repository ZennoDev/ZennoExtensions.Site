---
layout: docsMember
permalink: docs/Tab/WaitLoading/

categories:
    - Методы расширения Tab

title:          WaitLoading
member:
    type:       method
    name:       WaitLoading()
    summary:    'Выполняет ожидание полной прогрузки страницы.'
    returns:    'Тот же экземпляр Tab для множественных вызовов (Fluent Interface).'
    params:

---

```csharp
var tab = instance.ActiveTab;
tab.Go("ya.ru").WaitLoading();
```