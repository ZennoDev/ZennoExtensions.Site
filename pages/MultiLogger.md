---
layout: page
title: Работа с мультилогером
permalink: /MultiLogger
---

Мультилогер предоставляет возможности одновременного логирования в несколько источников.

***

Функционал работы с логированием находится в пространстве имен `ZennoExtensions.Loggers`.  
Для использования подключите пространства имен:
```csharp
using ZennoExtensions.Loggers;
using ZennoExtensions.Enums;
```

***

Чтобы начать работу с мультилоггером нужно получить единственный для всех потоков экземпляр класса `MultiLogger`.
Это можно сделать двумя способами:
+ обратившись к статическому методу `MultiLogger.GetInstance(IZennoPosterProjectModel project)`
+ или же вызвав метод расширения `project.GetLogger()`.


Далее по желанию можно настроить способы логирования через свойство `LogTo`, которое принимает перечисление типа `Logger`:

```csharp
var logger = project.GetLogger();
logger.LogTo = Logger.ProjectMaker | Logger.ZennoPoster;
```

Перечисление `Logger` содержит следующие значения:

- `ProjectMaker` — вывод сообщения в лог ProjectMaker;
- `ZennoPoster` — вывод сообщения в лог ZennoPoster; 
- `File` — логирование в файл;
- `Custom` — логирование через ваш логер.

По умолчанию значение `LogTo` это комбинация следующих логеров:  
`Logger.ProjectMaker | Logger.ZennoPoster | Logger.Custom`.

Теперь можно вызывать метод `MultiLog(string message, MessageType messageTypeType)`, который принимает сообщение и его тип. В зависимости от типа сообщения (`Error`, `Info`, `Warning`) меняется иконка в логе ProjectMaker и ZennoPoster.

```csharp
var logger = project.GetLogger();
logger.MultiLog("Тестовая запись в лог", MessageType.Warning);
```

Чтобы включить файловый логгер нужно установить путь к логу через свойство `FileLogPath` и добавить в способы логирования `Logger.File`:

```csharp
var logger = project.GetLogger();
logger.LogTo = Logger.ProjectMaker | Logger.ZennoPoster | Logger.File;
logger.FileLogPath = @"C:\mylog.txt";
logger.MultiLog("Тестовая запись в лог", MessageType.Error);
```

### Использование конкретных логеров

В мультилогере есть возможность логировать через конкретный логер невзирая на значения свойства `LogTo`:

- `LogToProjectMaker(string message, bool logToZennoPoster, MessageType messageTypeType)` — вывод сообщения в лог ProjectMaker;
- `LogToFile(string message, MessageType messageTypeType)` — логирование в файл, указанный в свойстве `FileLogPath`;
- `LogByCustom(string message, MessageType messageTypeType)` — логирование через набор ваших логеров.

***

## Создание своего логера

Вы можете добавить в мультилогер свой вариант логирования. 
Например, создадим логер, который будет выводить диалоговое окно с указанным сообщением.

Сначала нужно создать класс который будет реализовывать интерфейс `ILogger`:

```csharp
public class MessageBoxLogger : ILogger
{
	public void Log(string message, MessageType messageTypeType = MessageType.Info)
	{
		switch (messageTypeType)
		{
			case MessageType.Info:
				MessageBox.Show(message, "Информация", MessageBoxButtons.OK, MessageBoxIcon.Information);
				break;
			case MessageType.Warning:
				MessageBox.Show(message, "Внимание", MessageBoxButtons.OK, MessageBoxIcon.Warning);
				break;
			case MessageType.Error:
				MessageBox.Show(message, "Ошибка", MessageBoxButtons.OK, MessageBoxIcon.Error);
				break;
		}
	}       
}
```

Теперь нужно создать экземпляр класса `MessageBoxLogger` и добавить его в коллекцию `CustomLoggers` в мультилогере:

```csharp
var logger = project.GetLogger();
var messageBoxLogger = new MessageBoxLogger();
logger.CustomLoggers.Add(messageBoxLogger)
```

Чтобы воспользоваться нашим новым логером можно вызвать метод `LogByCustom`:

```csharp
logger.LogByCustom("Hello!");
```

Или можно активировать пользовательские логеры через свойство `LogTo` и вызвать метод `MultiLog`:

```csharp
logger.LogTo = Logger.ProjectMaker | Logger.ZennoPoster | Logger.Custom;
logger.MultiLog("Тестовая запись в лог", MessageType.Warning);
```