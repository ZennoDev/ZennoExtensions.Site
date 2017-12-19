---
layout: docsMember
permalink: docs/HtmlElement/GetVal/

categories:
    - Методы расширения HtmlElement

title:          GetVal
member:
    type:       method
    name:       GetVal()
    summary:    'Возвращает значение элемента. Обертка над GetValue().'
    returns:    'Значение элемента'
    params:

---

```csharp
var tab = instance.ActiveTab;
var value = tab.GetElementByXpath("//a").GetVal();
```