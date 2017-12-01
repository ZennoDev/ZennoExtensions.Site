---
layout: docsMember
permalink: /docs/AccountManager/ReleaseAccounts

categories:
    - Менеджер аккаунтов

title:          ReleaseAccounts
member:
    type:       method
    name:       ReleaseAccounts(System.Predicate{ZennoExtensions.AccountManager.Account} predicate)
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
manager.ReleaseAccounts(account =&gt;
!account.IsBusy   
&amp;&amp; DateTime.Now - account.LastExecution &gt; TimeSpan.FromHours(1));
```
