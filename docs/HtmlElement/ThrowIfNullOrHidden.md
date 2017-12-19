---
layout: docsMember
permalink: docs/HtmlElement/ThrowIfNullOrHidden/

categories:
    - Методы расширения HtmlElement

title:          ThrowIfNullOrHidden
member:
    type:       method
    name:       ThrowIfNullOrHidden(string exceptionMessage)
    summary:    'Бросает исключение, если елемент пуст (свойство IsVoid возвращает true) или скрыт.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.ThrowIfNullOrHidden("Элемент не найден.");
```