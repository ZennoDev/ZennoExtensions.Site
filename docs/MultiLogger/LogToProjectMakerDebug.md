---
layout: docsMember
permalink: docs/MultiLogger/LogToProjectMakerDebug/

categories:
    - Мультилогер

title:          LogToProjectMakerDebug
member:
    type:       method
    name:       LogToProjectMakerDebug(string message, bool logToZennoPoster,ZennoExtensions.Enums.MessageType messageType)
    summary:    'Вывод сообщения в лог ProjectMaker в режиме Debug.
Обертка над методами project.Send***ToLog.'
    returns:    'void'
    params:
        - name:  message
          value: 'Сообщение'
        - name:  logToZennoPoster
          value: 'Выводить ли сообщение в ZennoPoster&lsquo;e.'
        - name:  messageType
          value: 'Тип сообщения. По умолчанию MessageType.Info.'

---

```csharp
var logger = project.GetLogger();
logger.LogToProjectMakerDebug("Тестовая запись в лог");
```
