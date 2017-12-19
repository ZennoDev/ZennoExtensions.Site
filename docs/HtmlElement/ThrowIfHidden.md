---
layout: docsMember
permalink: docs/HtmlElement/ThrowIfHidden/

categories:
    - Методы расширения HtmlElement

title:          ThrowIfHidden
member:
    type:       method
    name:       ThrowIfHidden(string exceptionMessage)
    summary:    'Бросает исключение, если елемент скрыт.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.ThrowIfHidden("Элемент не доступен.");
```