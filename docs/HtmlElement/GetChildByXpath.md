---
layout: docsMember
permalink: docs/HtmlElement/GetChildByXpath/

categories:
    - Методы расширения HtmlElement

title:          GetChildByXpath
member:
    type:       method
    name:       GetChildByXpath(string number)
    summary:    'Поиск дочеренего элемента по XPath. Обертка над FindChildByXPath().'
    returns:    'void'
    params:
        - name:  number
          value: 'Номер совпадения'

---

```csharp
var tab = instance.ActiveTab;
var divElement = tab.GetElementByXpath("//div");
divElement.GetChildByXpath(".//a").Click();
```