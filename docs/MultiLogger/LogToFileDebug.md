---
layout: docsMember
permalink: docs/MultiLogger/LogToFileDebug/

categories:
    - Мультилогер

title:          LogToFileDebug
member:
    type:       method
    name:       LogToFileDebug(System.String message,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в файл в режиме Debug.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogToFile("Тестовая запись в лог");
```
