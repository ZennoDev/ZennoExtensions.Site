---
layout: docsMember
permalink: /docs/Browser/Setup

categories:
    - Настройка браузера

title:          Setup
member:
    type:       method
    name:       Setup(ZennoExtensions.Browser.Model.Profile profile,ZennoLab.CommandCenter.Instance instance,ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel project)
    summary:    'Применяет конфигурацию к ZennoPoster&lsquo;y.'
    returns:    'void'
    params:
        - name:  profile
          value: 'Профиль браузера.'
        - name:  instance
          value: 'Экземпляр <see cref="T:ZennoLab.CommandCenter.Instance" />'
        - name:  project
          value: 'Экземпляр <see cref="T:ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel" />'

---

```csharp
// Создаем объект правил генерации
var generationRules = new GenerationRules();

// Указываем чтобы использовался случайно Firefox или Chrome
generationRules.BrowserType = BrowserType.Firefox | BrowserType.Chrome;

// Генерируем профиль браузера
var profile = BrowserManager.Generate();

// Применяем к ZennoPoster'у
BrowserManager.Setup(profile, instance, project);
```
