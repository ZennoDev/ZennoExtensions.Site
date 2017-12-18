---
layout: docsMember
permalink: docs/MultiLogger/LogByCustomDebug/

categories:
    - Мультилогер

title:          LogByCustomDebug
member:
    type:       method
    name:       LogByCustomDebug(System.String message,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в режиме Debug через набор пользовательских логгеров, установленных в свойстве CustomLoggers.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogByCustomDebug("Тестовая запись в лог");
```
