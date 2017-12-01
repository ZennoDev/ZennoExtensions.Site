---
layout: docsMember
permalink: /docs/MultiLogger/LogToProjectMaker

categories:
    - Мультилогер

title:          LogToProjectMaker
member:
    type:       method
    name:       LogToProjectMaker(System.String message,System.Boolean logToZennoPoster,ZennoExtensions.Enums.MessageType messageTypeType)
    summary:    'Вывод сообщения в лог ProjectMaker.
Обертка над методами project.Send***ToLog.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение'
        - name:  logToZennoPoster
          value: 'Выводить ли сообщение в ZennoPoster&lsquo;e.'
        - name:  messageTypeType
          value: 'Тип сообщения.'

---

```csharp
var logger = project.GetLogger();
logger.LogToProjectMaker("Тестовая запись в лог");
```
