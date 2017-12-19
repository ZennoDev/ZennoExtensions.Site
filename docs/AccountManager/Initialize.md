---
layout: docsMember
permalink: docs/AccountManager/Initialize/

categories:
    - Менеджер аккаунтов

title:          Initialize
member:
    type:       method
    name:       Initialize(string accountsPath, string configPath, string accountStringSeparator, bool removeObsoleteAccountsInConfig)
    summary:    'Производит инициализацию менеджера аккаунтов.
Сопоставляет существующую конфигурацию аккаунтов или создает новую для файла с аккаунтами.'
    returns:    'Экземпляр AccountManager.'
    params:
        - name:  accountsPath
          value: 'Путь к файлу с аккаунтами.'
        - name:  configPath
          value: 'Путь к файлу с конфигурацией.'
        - name:  accountStringSeparator
          value: 'Разделитель для строки аккаунта.'
        - name:  removeObsoleteAccountsInConfig
          value: 'Если true, то из конфигурации удаляются аккаунты, которых нет в файле аккаунтов.'

---

```csharp
string accountsPath = @"C:\accounts.txt";
string configPath = accountsPath + ".config.xml";
var manager = AccountManager.GetInstance();
manager.Initialize(accountsPath, configPath);
```
