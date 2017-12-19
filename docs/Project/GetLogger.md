---
layout: docsMember
permalink: docs/Project/GetLogger/

categories:
    - Методы расширения IZennoProjectModel

title:          GetLogger
member:
    type:       method
    name:       GetLogger()
    summary:    'Возвращает объект мультилоггера.'
    returns:    'Экземпляр ZennoExtensions.Loggers.MultiLogger'
    params:

---

```csharp
var logger = project.GetLogger();
logger.FileLogPath = @"C:\logs.txt";

// Выводи сообщение в лог ZennoPoster'а и в файл
logger.MultiLog("Тестовое сообщение.");
```