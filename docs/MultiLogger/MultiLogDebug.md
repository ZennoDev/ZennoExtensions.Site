---
layout: docsMember
permalink: docs/MultiLogger/MultiLogDebug/

categories:
    - Мультилогер

title:          MultiLogDebug
member:
    type:       method
    name:       MultiLogDebug(string message, ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в режиме Debug через набор логгеров, установленных через свойство LogTo.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger(); 
logger.MultiLogDebug("Тестовая запись в лог", MessageType.Warning);
```
