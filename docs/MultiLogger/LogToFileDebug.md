---
layout: docsMember
permalink: docs/MultiLogger/LogToFileDebug/

categories:
    - Мультилогер

title:          LogToFileDebug
member:
    type:       method
    name:       LogToFileDebug(string message, ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в файл в режиме Debug.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogToFileDebug("Тестовая запись в лог");
```
