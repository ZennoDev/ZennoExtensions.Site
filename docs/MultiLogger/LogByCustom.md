---
layout: docsMember
permalink: /docs/MultiLogger/LogByCustom

categories:
    - Мультилогер

title:          LogByCustom
member:
    type:       method
    name:       LogByCustom(System.String message,ZennoExtensions.Enums.MessageType messageTypeType)
    summary:    'Логирование через набор пользовательских логгеров, установленных в свойстве CustomLoggers.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageTypeType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogByCustom("Тестовая запись в лог");
```
