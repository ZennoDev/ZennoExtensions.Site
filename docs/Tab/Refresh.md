---
layout: docsMember
permalink: docs/Tab/Refresh/

categories:
    - Методы расширения Tab

title:          Refresh
member:
    type:       method
    name:       Refresh()
    summary:    'Выполняет обновление текущей страницы.'
    returns:    'Тот же экземпляр Tab для множественных вызовов (Fluent Interface).'
    params:

---

```csharp
var tab = instance.ActiveTab;
tab.Refresh().GetElementByXpath("//a").ClickOn().ParentTab.WaitLoading();
```