---
layout: docsMember
permalink: docs/AccountManager/GetAccount/

categories:
    - Менеджер аккаунтов

title:          GetAccount
member:
    type:       method
    name:       GetAccount(System.Predicate{ZennoExtensions.AccountManager.Account} predicate,System.Boolean throwExceptionIfNoFreeAccounts,System.String exceptionMessage)
    summary:    'Возвращает аккаунт, удовлетворяющий предикату.'
    returns:    'Аккаунт.'
    params:
        - name:  predicate
          value: 'Предикат.'
        - name:  throwExceptionIfNoFreeAccounts
          value: 'Если true и все аккаунты заняты, то метод выбросит исключение.'
        - name:  exceptionMessage
          value: 'Сообщение исключения'

---

```csharp
var account = manager.GetAccount(
    acc => !acc.IsBusy 
           && !acc.IsMissed 
           && DateTime.Now - acc.LastExecution > TimeSpan.FromHours(12));
```
