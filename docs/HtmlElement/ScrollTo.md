---
layout: docsMember
permalink: docs/HtmlElement/ScrollTo/

categories:
    - Методы расширения HtmlElement

title:          ScrollTo
member:
    type:       method
    name:       ScrollTo()
    summary:    'Прокручивает струницу к текущему элементу. Обертка над ScrollIntoView().'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.ScrollTo().Click();
```