---
layout: docsMember
permalink: docs/MultiLogger/LogToProjectMaker/

categories:
    - Мультилогер

title:          LogToProjectMaker
member:
    type:       method
    name:       LogToProjectMaker(string message, bool logToZennoPoster,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Вывод сообщения в лог ProjectMaker.
Обертка над методами project.Send***ToLog.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение'
        - name:  logToZennoPoster
          value: 'Выводить ли сообщение в ZennoPoster&lsquo;e. По умолчанию true.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogToProjectMaker("Тестовая запись в лог");
```
