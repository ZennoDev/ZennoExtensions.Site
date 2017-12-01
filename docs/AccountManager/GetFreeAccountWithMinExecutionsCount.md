---
layout: docsMember
permalink: /docs/AccountManager/GetFreeAccountWithMinExecutionsCount

categories:
    - Менеджер аккаунтов

title:          GetFreeAccountWithMinExecutionsCount
member:
    type:       method
    name:       GetFreeAccountWithMinExecutionsCount(System.Boolean throwExceptionIfNoFreeAccounts)
    summary:    'Возвращает свободный аккаунт с наименьшим количеством запусков.'
    returns:    'Аккаунт.'
    params:
        - name:  throwExceptionIfNoFreeAccounts
          value: 'Если true и все аккаунты заняты, то метод выбросит исключение.'

---

```csharp
var account = manager.GetFreeAccountWithMinExecutionsCount();
    
if (account == null)
    project.SendInfoToLog("Все аккаунты заняты", true); 
    
project.SendInfoToLog("Логин: " + account.Login, true); 
project.SendInfoToLog("Пароль: " + account.Password, true);
```
