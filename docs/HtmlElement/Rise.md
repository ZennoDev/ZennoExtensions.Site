---
layout: docsMember
permalink: docs/HtmlElement/Rise/

categories:
    - Методы расширения HtmlElement

title:          Rise
member:
    type:       method
    name:       Rise(ZennoExtensions.Enums.Event event, ZennoExtensions.Enums.Emulation emulation)
    summary:    'Выполняет событие для элемента.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  event
          value: 'Выполняемое событие.'
        - name:  emulation
          value: 'Уровень эмуляции. По умолчанию EmulationLevel.Full.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.Rise(Event.Click).ParentTab.WaitLoading();
```