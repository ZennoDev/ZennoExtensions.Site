---
layout: docsMember
permalink: docs/HtmlElement/GetAttr/

categories:
    - Методы расширения HtmlElement

title:          GetAttr
member:
    type:       method
    name:       GetAttr(string attrName)
    summary:    'Получает значение атрибуа элемента. Обертка над GetAttribute().'
    returns:    'Значение атрибута'
    params:
        - name:  attrName
          value: 'Название атрибута.'

---

```csharp
var tab = instance.ActiveTab;
var url = tab.GetElementByXpath("//a").GetAttr("href");
```