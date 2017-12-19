---
layout: docsMember
permalink: docs/AccountManager/ReleaseAccounts/

categories:
    - Менеджер аккаунтов

title:          ReleaseAccounts
member:
    type:       method
    name:       ReleaseAccounts(System.Predicate&lt;ZennoExtensions.AccountManager.Account&gt; predicate)
    summary:    'Освобождает все аккаунты для которых предикат возвращает true.'
    returns:    'void'
    params:
        - name:  predicate
          value: 'Предикат.'

---

```csharp
string accountsPath = @"C:\accounts.txt";
string configPath = accountsPath + ".config.xml";
var manager = AccountManager.GetInstance();
manager.Initialize(accountsPath, configPath);
manager.ReleaseAccounts(acc =>
    !acc.IsBusy   
    && DateTime.Now - acc.LastExecution > TimeSpan.FromHours(1));
```
