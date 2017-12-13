---
layout: docsMember
permalink: docs/MultiLogger/MultiLogDebug/

categories:
    - Мультилогер

title:          MultiLogDebug
member:
    type:       method
    name:       MultiLogDebug(System.String message,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в режиме Debug через набор логгеров, установленных через свойство LogTo.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. Не обязательный параметр, по умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger(); 
logger.MultiLogDebug("Тестовая запись в лог", MessageType.Warning);
```
