---
layout: page
title: Работа с менеджером аккаунтов
permalink: /AccountManager
---

Менеджер аккаунтов предоставляет функционал многопоточной работы со списком аккаунтов. 

***

Функционал менеджера аккаунтов находится в пространстве имен `ZennoExtensions.AccountManager`.  
Для использования подключите пространство имен:
```csharp
using ZennoExtensions.AccountManager;
```

***

## Инициализация

Чтобы приступить к работе с менеджером аккаунтов нужно обратиться к статическому методу `AccountManager.GetInstance()`, который вернет единственный для всех потоков экземпляр менеджера.
 
Затем нужно инициализировать экземпляр менеджера вызвав метод `Initialize` и указав путь к файлу с аккаунтами и путь до файла конфигурации аккаунтов.

```csharp
string accountsPath = @"C:\accounts.txt";
string configPath = accountsPath + ".config.xml";
var manager = AccountManager.GetInstance();
manager.Initialize(accountsPath, configPath);
```

Файл конфигурации представляет из себя Xml-файл, который генерируется на основе списка аккаунтов.
Конфигурация содержит данные, которые закрепляются за аккаунтами, например, прокси, а также набор свойств, благодаря которым потоки могут брать незанятые и незабаненные аккаунты .

#### Пример конфигурации:

```xml
<?xml version="1.0"?>
<Accounts xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Account Id="1" Login="user1" Password="pass" Order="135" IsBusy="false" IsBanned="false" LastExecution="16-11-2017 10:35:38" />
  <Account Id="3" Login="user3" Password="pass" Order="131" IsBusy="false" IsBanned="false" LastExecution="16-11-2017 10:35:37" />
  <Account Id="7" Login="user2" Password="pass" Order="132" IsBusy="false" IsBanned="false" LastExecution="16-11-2017 10:35:38" />
</Accounts>
```

+ Свойство `Order` показывает приоритет аккаунта для работы. Чем меньше его номер, тем скорее он вступит в работу. После того, как аккаунт закончит работу ему присваивается максимальный `Order` среди существующих аккаунтов. Таким образом работа между всеми аккаунтами распределяется равномерно, даже если пользователь добавил новые аккаунты в файл во время выполнения шаблона.
+ Свойство `IsBusy` показывает находится ли данный аккаунт сейчас в работе. 
+ Свойство `IsBanned` показывает можно ли вообще брать данный аккаунт для работы. Вы можете устанавливать это свойство из кода или же пользователь может редактировать конфигурацию. 
+ Свойство `LastExecution` показывает когда в последний раз данный аккаунт находился в работе.

***

## Получение аккаунтов

После того как инициализация менеджера аккаунтов произведена можно вызывать методы, которые возвращают аккаунты:

- `GetFreeAccountWithMinExecutionsCount(bool throwExceptionIfNoFreeAccounts = false)` — возвращает свободный и незабаненный аккаунт с минимальным количеством запусков, т.е. с минимальным значением свойства `Order`. Если свободных аккаунтов нет, то вернется `null`. В параметры метода можно передать `true`, тогда в случае отсутствия свободных аккаунтов будет генерироваться исключение.
    ```csharp
    var account = manager.GetFreeAccountWithMinExecutionsCount();
    
    if (account == null)
        project.SendInfoToLog("Все аккаунты заняты", true); 
    
    project.SendInfoToLog("Логин: " + account.Login, true); 
    project.SendInfoToLog("Пароль: " + account.Password, true); 
    ```
- `GetAccount(Predicate<Account> predicate)` — возвращает аккаунт, удовлетворяющий предикату.  
Например, можно получить свободный и незабаненный аккаунт, который не был в работе более 12-и часов:
    ```csharp
    var account = manager.GetAccount(
        account => !account.IsBusy 
                && !account.IsBanned 
                && DateTime.Now - account.LastExecution > TimeSpan.FromHours(12)); 
    ```
    
***

## Освобождение аккаунтов

Методы получения аккаунтов помечают найденный аккаунт как занятый `account.IsBusy = true`, чтобы другие потоки не могли взять данный аккаунт.
Поэтому после окончания работы с аккаунтом нужно освободить его для других потоков.

Для этого нужно вызвать метод `Release` на объекте аккаунта:

```csharp
var account = manager.GetFreeAccountWithMinExecutionsCount(); 
if(account != null)
{
    // Какая-то работа с аккаунтом
    // ...
    
    // Освобождаем аккаунт
    account.Release();
}
```

Метод `Release` устанавливает свойство `IsBusy = false`, обновляет дату последнего запуска аккаунта и обновляет конфигурацию аккаунтов. Таким образом все внесенные изменения для аккаунта сохраняются и все потоки работают с актуальными данными.

Может случиться внештатная ситуация, например когда ZennoPoster вылетит, и тогда есть вероятность, что аккаунт не успеет разблокироваться и в конфигурации так и останется заблокированным для других потоков.

Чтобы избежать подобной ситуации рекомендуется после инициализации менеджера вызывать метод `ReleaseAccounts(Predicate<Account> predicate)`, который освобождает все аккаунты, удовлетворяющие предикату. 

Пример, в котором освобождаются все аккаунты простаивающие более одно часа:

```csharp
string accountsPath = @"C:\accounts.txt";
string configPath = accountsPath + ".config.xml";
var manager = AccountManager.GetInstance();
manager.Initialize(accountsPath, configPath);
manager.ReleaseAccounts(account => !account.IsBusy                                                   
                                   && DateTime.Now - account.LastExecution > TimeSpan.FromHours(1)); 
```

***

## Закрепление данных за аккаунтом

Чтобы закрепить прокси за аккаунтом достаточно указать экземпляр прокси и после того, как конфигурация будет сохранена после вызова метода `account.Release()` (или `account.SaveChanges()`, который обновляет данные аккаунта в конфигурации) в файле аккаунта за аккаунтом закрепятся новые данные.

Пример:

```csharp
var freeAccount = manager.GetFreeAccountWithMinExecutionsCount();
freeAccount.Proxy = new Proxy
{
    Ip = "127.0.0.1",
    Port = 80,
    Scheme = "socks5"
}; 

freeAccount.SaveChanges(); // Сохраняем изменения в аккаунте.
```

После выполнения этого кода за аккаунтом закрепится прокси:

```xml
<Account Id="3" Login="user3" Password="password"
         Order="136" IsBusy="false" IsBanned="false" LastExecution="28-11-2017 15:33:48">
    <Proxy Ip="127.0.0.1" Port="80" Scheme="socks5" />
</Account>
```

Таким образом вы можете закреплять за аккаунтами и свои данные. Достаточно добавить новые свойства, которые будут представлять ваши данные,  в клаcc `Account`. 
