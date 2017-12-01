---
layout: docsMember
permalink: /docs/MultiLogger/MultiLog

categories:
    - Мультилогер

title:          MultiLog
member:
    type:       method
    name:       MultiLog(System.String message,ZennoExtensions.Enums.MessageType messageTypeType)
    summary:    'Логирование через набор логгеров, установленных через свойство LogTo.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageTypeType
          value: 'Тип сообщения. Не обязательный параметр, по умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.MultiLog("Тестовая запись в лог", MessageType.Warning);
```
