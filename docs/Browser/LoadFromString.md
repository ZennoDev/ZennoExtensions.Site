---
layout: docsMember
permalink: /docs/Browser/LoadFromString

categories:
    - Настройка браузера

title:          LoadFromString
member:
    type:       method
    name:       LoadFromString(System.String data)
    summary:    'Загружает объект профиля браузера, сохраненный в строку.'
    returns:    'Профиль браузера'
    params:
        - name:  data
          value: 'Строка, содержащая сохраненный объект.'

---

```csharp
// Загружаем из строки
string profile = BrowserManager.LoadFromString(savedProfile);

// Применяем к ZennoPoster'у
BrowserManager.Setup(profile, instance, project);
```
