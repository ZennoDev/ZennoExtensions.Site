---
layout: docsMember
permalink: docs/Tab/WaitFor/

categories:
    - Методы расширения Tab

title:          WaitFor
member:
    type:       method
    name:       WaitFor(Func&lt;bool&gt; predicate, int timeout)
    summary:    'Выполняет ожидание, пока предикат не вернет true, либо до истечения таймаута.'
    returns:    'Тот же экземпляр Tab для множественных вызовов (Fluent Interface).'
    params:
        - name:  predicate
          value: 'Условное выражение.'
        - name:  timeout
          value: 'Длительность проверки выражения в миллисекундах. По умолчанию 5000.'

---

```csharp
var tab = instance.ActiveTab;

// Кнопка, открвающая окно попапа
Func<HtmlElement> EditProfileBtn = () => tab.GetElementByXpath("//a[contains(@hrefattrs,'EditUserProfile')]");
// Окно
Func<HtmlElement> EditProfilePopup = () => tab.GetElementByXpath("//div[contains(@id,'EditUser')]");

EditProfileBtn().Click();

// Ожидаем появления попапа 10 секунд
tab.WaitFor(() => !EditProfilePopup().IsHidden(), 10000);
```

Этот метод удобен в использовании при динамическом изменении страницы, когда нужно дождаться появления, исчезновения или изменения элемента.