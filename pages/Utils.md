---
layout: page
title: Вспомогательные классы
permalink: /Utils
---

Для использования подключите пространства имен:

```csharp
using ZennoExtensions.Utils;
```

***

## Класс Throw

Предоставляет возможность выбрасывать исключения и выполнять определенные действия перед их срабатыванием.

Чтобы выкинуть исключение достаточно вызвать метод `Throw.Exception("message")`, указав сообщение исключения, либо пустую строку или `null`. После срабатывания исключения экшн перейдет по ветви BabEnd, и если ветвь не ведет ни на какой другой экшн, в лог будет выведено указанное сообщение с типом `Error` и информация о классе Exception.

```csharp
// ...
if (isBanned)
    Throw.Exception("Аккаунт заблокирован");
```

Помимо вышеуказаного метода, исключения также выкидываются различными методами расширения локальных переменных, например, `project.Variables["name"].ThrowIfEmpty("message");`.

Вы можете задать свою обработку этих исключений. Для этого в классе `Throw` есть свойство `Action<ExceptionArgs> InvokeBeforeException`. Давайте укажем, чтобы сообщения выводились в лог с типом `Warning` и писались в файл логов:

```csharp
var logger = project.GetLogger();
logger.LogTo = Logger.File | Logger.ZennoPoster;
logger.FileLogPath = @"C:\logs.txt";

// Указываем, чтобы перед срабатыванием исключения выполнялась запись в лог постера и в файл
Throw.InvokeBeforeException = args =>
    logger.MultiLog(args.Message, MessageType.Warning);

Throw.Exception("Это сообщение будет выведено как Warning");
```

После этого достаточно направить ветвь BadEnd'a на пустой экшн C#, чтобы сообщение с исключением типа `Error` не выводилось в лог.

## Класс StringParser

Позволяет разбирать строки на части по указанному шаблону.

Например, есть строк с прокси `123.123.123.123:1010;myLogin;myPassword;что-то-еще`. Нужно получить только данные прокси и сформировать для установки в инстанс.  
Распарсим данный файл:

```csharp
var str = "123.123.123.123:1010;myLogin;myPassword;что-то-еще";

// Задаем шаблон для разбора строки
var pattern = "proxy;login;password;";

var proxyDictionary = StringParser.Parse(str, pattern);

var login = proxyDictionary["login"];          // myLogin
var password = proxyDictionary["password"];    // myPassword
var proxy = proxyDictionary["proxy"];          // 123.123.123.123:1010

instance.SetProxy(login + ":" + password + "@" + proxy)
```

Метод `Parse` принимает исходную строку и шаблон, по которому нужно разбирать строку. Шаблон состоит из ключей и разделителей. Во время разбора создается словарь, в который кладутся заданные в шаблоне ключи и соответствующие данные в строке.