---
layout: docsMember
permalink: docs/Browser/Save/

categories:
    - Настройка браузера

title:          Save
member:
    type:       method
    name:       Save(ZennoExtensions.Browser.Model.Profile profile,ZennoLab.CommandCenter.Instance instance)
    summary:    'Сериализует и сохраняет объект профиля браузера.'
    returns:    'Строка с сохраненным объектом профиля браузера.'
    params:
        - name:  profile
          value: 'Объект профиля браузера.'
        - name:  instance
          value: 'Экземпляр Instance.'

---

```csharp
// Генерируем профиль браузера
var profile = BrowserManager.Generate();

// Сохраняем в переменную
string savedProfile = BrowserManager.Save(profile, instance);
```
