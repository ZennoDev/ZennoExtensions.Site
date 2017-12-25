---
layout: docsMember
permalink: docs/BrowserManager/Generate/

categories:
    - Настройка браузера

title:          Generate
member:
    type:       method
    name:       Generate(ZennoExtensions.BrowserManager.GenerationRules generationRules)
    summary:    'Генерация профиля браузера.'
    returns:    'Заполненый профиль браузера.'
    params:
        - name:  generationRules
          value: 'Набор правил и данных для генерации. Не обязательный параметр.'

---

```csharp
// Создаем объект правил генерации
var generationRules = new GenerationRules();

// Указываем чтобы использовался случайно Firefox или Chrome
generationRules.BrowserType = BrowserType.GoogleChrome | BrowserType.MozillaFirefox;

// Генерируем профиль браузера
var profile = BrowserManager.Generate();

// Применяем к ZennoPoster'у
BrowserManager.Setup(profile, instance, project);
```
