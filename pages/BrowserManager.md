---
layout: page
title: Менеджер браузера
permalink: /BrowserManager

---

BrowserManager предоставляет возможность генерировать набор параметров (профиль браузера), применять к инстансу и сохранять для повторного использования. 

***

Функционал настройки браузера находится в пространстве имен `ZennoExtensions.BrowserManager`.  
Для использования подключите пространства имен:
```csharp
using ZennoExtensions.BrowserManager;
using ZennoExtensions.BrowserManager.Model;
using ZennoExtensions.BrowserManager.Model.Filters;
using ZennoExtensions.BrowserManager.Generation.Rules;
```

***

## Генерируемые параметры

Менеджер браузера может генерировать следующие параметры:

+ Используемый браузер (Firefox, Chrome)
+ Используемое устройство (на данный момент только Windows)
+ Настройки браузера:
    + Использование JavaScript
    + Блокировка рекламы
    + Использование веб хранилищ (LocalStorage, SessionStorage, Global Storage, Database Storage)
    + Использование IndexedDb
    + Использование WebGL
    + Использование плагинов
    + DoNotTrack
    + Подмена часового пояса
    + Эмуляция WebRTC
    + Эмуляция Canvas
+ Свойства навигатора и HTTP заголовки

***

## Генерация

Для генерации профиля браузера необхдимо вызвать метод `BrowserManager.Generate(generationRules)`, который принимает 1 необязательный параметр - правила генерации.

```csharp
var profile = BrowserManager.Generate();
```

Вы можете настроить как именно производить генерацию, передав объект правил в метод `Generate`:

```csharp
var rules = new GenerationRules();
rules.BrowserType = BrowserType.MozillaFirefox;
rules.Settings.DoNotTrack = BoolFilter.True | BoolFilter.False;
rules.Settings.CanvasRenderMode = CanvasWorkMode.Emulate;
rules.Navigator.GenerateHardwareConcurrency = BoolFilter.True;
rules.Screen.UseScreenResolutionGeneration = BoolFilter.True;

var profile = BrowserManager.Generate(rules);
```

Обратите внимание, свойствам, принимающим перечисление, можно передать сразу несколько значений. Тогда во время генерации будет выбрано случайное из переданных значений:
```csharp
rules.Settings.DoNotTrack = BoolFilter.True | BoolFilter.False;
```

После генерации профиля его нужно применить к ZennoPoster'у:
```csharp
BrowserManager.Setup(profile, instance, project);
```
После применения все параметры инстанса будут установлены в соответствии со сгенерированными.

***

## Сохранение и загрузка

Если вам необходимо повторно использовать сгенерированные параметры, вы можете сохранить их.
Сохранение рекомендуется делать перед самым завершением работы шаблона. В противном случае данные полученные во время серфинга (куки, данные хранилищ..) не будут сохранены.

```csharp
// Сохраняем в файл
string path = "C:\\1.json";
BrowserManager.Save(profile, instance, path);
```

Для повторного использования нужно загрузить и снова применить профиль:
```csharp
string path = "C:\\1.json";
var profile = BrowserManager.Load(path);
BrowserManager.Setup(profile, instance, project);
```