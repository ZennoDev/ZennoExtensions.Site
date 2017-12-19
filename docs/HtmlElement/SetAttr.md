---
layout: docsMember
permalink: docs/HtmlElement/SetAttr/

categories:
    - Методы расширения HtmlElement

title:          SetAttr
member:
    type:       method
    name:       SetAttr(System.String attrName,System.String attrValue)
    summary:    'Устанавливает значение атрибуа элемента.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  attrName
          value: 'Название атрибута.'
        - name:  attrValue
          value: 'Устанавливаемое значение.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.SetAttr("href", "ya.ru").Click();
```