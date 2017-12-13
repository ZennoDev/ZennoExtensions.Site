---
layout: docsMember
permalink: docs/MultiLogger/LogToProjectMakerDebug/

categories:
    - Мультилогер

title:          LogToProjectMakerDebug
member:
    type:       method
    name:       LogToProjectMakerDebug(System.String message,System.Boolean logToZennoPoster,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Вывод сообщения в лог ProjectMaker в режиме Debug.
Обертка над методами project.Send***ToLog.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение'
        - name:  logToZennoPoster
          value: 'Выводить ли сообщение в ZennoPoster&lsquo;e.'
        - name:  messageType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogToProjectMaker("Тестовая запись в лог");
```
