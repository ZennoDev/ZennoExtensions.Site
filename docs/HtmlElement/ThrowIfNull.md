---
layout: docsMember
permalink: docs/HtmlElement/ThrowIfNull/

categories:
    - Методы расширения HtmlElement

title:          ThrowIfNull
member:
    type:       method
    name:       ThrowIfNull(string exceptionMessage)
    summary:    'Бросает исключение, если элемент пуст (свойство IsVoid возвращает true).'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  exceptionMessage
          value: 'Сообщение исключения.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.ThrowIfNull("Элемент не найден.");
```