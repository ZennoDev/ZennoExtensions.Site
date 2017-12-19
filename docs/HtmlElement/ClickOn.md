---
layout: docsMember
permalink: docs/HtmlElement/ClickOn/

categories:
    - Методы расширения HtmlElement

title:          ClickOn
member:
    type:       method
    name:       ClickOn()
    summary:    'Выполняет клик по элементу.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a").ClickOn();
```