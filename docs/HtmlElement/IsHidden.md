---
layout: docsMember
permalink: docs/HtmlElement/IsHidden/

categories:
    - Методы расширения HtmlElement

title:          IsHidden
member:
    type:       method
    name:       IsHidden()
    summary:    'Проверяет скрыт ли элемент.'
    returns:    'true/false'
    params:

---

```csharp
var tab = instance.ActiveTab;
var divElement = tab.GetElementByXpath("//div");

if (divElement.IsHidden())
    project.SendInfoToLog("Элемент скрыт.", true);
```