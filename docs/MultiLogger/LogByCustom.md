---
layout: docsMember
permalink: docs/MultiLogger/LogByCustom/

categories:
    - Мультилогер

title:          LogByCustom
member:
    type:       method
    name:       LogByCustom(string message, ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование через набор пользовательских логгеров, установленных в свойстве CustomLoggers.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogByCustom("Тестовая запись в лог");
```
