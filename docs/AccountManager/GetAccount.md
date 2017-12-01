---
layout: docsMember
permalink: docs/AccountManager/GetAccount/

categories:
    - Менеджер аккаунтов

title:          GetAccount
member:
    type:       method
    name:       GetAccount(System.Predicate{ZennoExtensions.AccountManager.Account} predicate)
    summary:    'Возвращает аккаунт, удовлетворяющий предикату.'
    returns:    'Аккаунт.'
    params:
        - name:  predicate
          value: 'Предикат.'

---

```csharp
var account = manager.GetAccount(
    account =&gt; !account.IsBusy 
&amp;&amp; !account.IsBanned 
&amp;&amp; DateTime.Now - account.LastExecution &gt; TimeSpan.FromHours(12));
```
