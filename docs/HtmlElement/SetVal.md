---
layout: docsMember
permalink: docs/HtmlElement/SetVal/

categories:
    - Методы расширения HtmlElement

title:          SetVal
member:
    type:       method
    name:       SetVal(string value, ZennoExtensions.Enums.Emulation emulation, bool useSelectedItems)
    summary:    'Устанавливает значение элемента.'
    returns:    'Тот же экземпляр HtmlElement для множественных вызовов (Fluent Interface).'
    params:
        - name:  value
          value: 'Устанавливаемое значение.'
        - name:  emulation
          value: 'Уровень эмуляции. По умолчанию EmulationLevel.Full.'
        - name:  useSelectedItems
          value: 'true, если вам нужно использовать автоматическое заполнение стандартных полей типа
Select, в противном случае - false.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
linkElement.SetVal("text").Click();
```