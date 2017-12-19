---
layout: docsMember
permalink: docs/MultiLogger/LogToFile/

categories:
    - Мультилогер

title:          LogToFile
member:
    type:       method
    name:       LogToFile(string message, ZennoExtensions.Enums.MessageType messageType)
    summary:    'Логирование в файл.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogToFile("Тестовая запись в лог");
```
