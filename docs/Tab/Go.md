---
layout: docsMember
permalink: docs/Tab/Go/

categories:
    - Методы расширения Tab

title:          Go
member:
    type:       method
    name:       Go(string url, string referer)
    summary:    'Выполняет переход по указанному Url. Обертка над Navigate.'
    returns:    'Тот же объект ZennoLab.CommandCenter.Tab для множественных вызовов (Fluent Interface).'
    params:
        - name:  url
          value: 'Ссылка.'
        - name:  referer
          value: 'Реферер.'

---

```csharp
var tab = instance.ActiveTab;

tab.Go("ya.ru").WaitLoading()
   .Go("google.ru").WaitLoading();
```