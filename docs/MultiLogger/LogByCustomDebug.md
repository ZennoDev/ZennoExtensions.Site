---
layout: docsMember
permalink: docs/MultiLogger/LogByCustomDebug/

categories:
    - Мультилогер

title:          LogByCustomDebug
member:
    type:       method
    name:       LogByCustomDebug(string message, ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в режиме Debug через набор пользовательских логгеров, установленных в свойстве CustomLoggers.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogByCustomDebug("Тестовая запись в лог");
```
