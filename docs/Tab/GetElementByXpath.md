---
layout: docsMember
permalink: docs/Tab/GetElementByXpath/

categories:
    - Методы расширения Tab

title:          GetElementByXpath
member:
    type:       method
    name:       GetElementByXpath(string xpath, int number)
    summary:    'Находит элемент по XPath. Обертка над FindElementByXPath.'
    returns:    'Найденный элемент.'
    params:
        - name:  xpath
          value: 'XPath.'
        - name:  number
          value: 'Номер совпадения.'

---

```csharp
var tab = instance.ActiveTab;
var linkElement = tab.GetElementByXpath("//a");
```