---
layout: docsMember
permalink: /docs/MultiLogger/LogToFile

categories:
    - Мультилогер

title:          LogToFile
member:
    type:       method
    name:       LogToFile(System.String message,ZennoExtensions.Enums.MessageType messageTypeType)
    summary:    'Логирование в файл.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение.'
        - name:  messageTypeType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogToFile("Тестовая запись в лог");
```
