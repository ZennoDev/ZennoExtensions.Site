---
layout: page
title: Методы расширения
permalink: /ExtensionMethods
---

***

Для использования методов расширения подключите пространство имен:
```csharp
using ZennoExtensions.Extensions;
```

***

## Работа с методами расширения локальных переменных

Методы расширения локальных переменных делятся на три категории:

1. Методы `IsXXX` проверяют значение переменной на соответствие XXX и возвращают `true` или `false`.
Например, `IsInt()` проверяет является ли значение переменной целым числом:

    ```csharp
    bool isInt = project.Variables["MyVariableName"].IsInt();	
    if(isInt)
    {
        project.SendInfoToLog("Переменная MyVariableName является целым числом.", true);
    }
    ```

2. Методы `ToXXX` конвертируют строковое значение переменной в XXX, где XXX — тип в который производится конвертация.
Например, метод `ToDouble` конвертирует значение переменной в `double`:
  
    ```csharp
    double value =  project.Variables["MyVariableName"].ToDouble();
    ```

3. Методы `ThrowIfXXX` выбрасывают исключения, если выполняется условие XXX. В метод можно передать сообщение, с которым выброситься исключение. Если сообщение не задано, то будет использоваться сообщение по умолчанию.

    ```csharp
    project.Variables["MyVariableName"].ThrowIfEmpty("Переменная не задана.");
    ```

<br />
 Методы `ThrowIfXXX` можно объединять в цепочки, чтобы проверять переменную на соответствие нескольким условиям. Этот подход удобен при проверке данных, которые указывает пользователь во входных настройках:

```csharp
string accountsPath = project.Variables["AccountsPath"]
                                 .ThrowIfEmpty("Путь к файлу аккаунтов не задан.")
                                 .ThrowIfFileNotExists("Файл аккаунтов не найден.")
                                 .ThrowIfTextFileIsEmpty("Файл аккаунтов пуст."  )
                                 .Value;
```

Также есть возможность указать свой метод, который будет вызываться прежде, чем метод `ThrowIfXXX` выбросит исключение. Это можно использовать при логировании.
 
Для этого нужно задать статическое свойство `InvokeBeforeExceptionThrowing` класса `Settings`. Метод принимает параметр типа `ExceptionArgs`, которые содержит имя метода, который намерен выбросить исключение, сообщение исключения и переменную, которая не прошла проверку.

```csharp
Settings.InvokeBeforeExceptionThrowing = args =>
{
    string logMessage = "При проверке переменной " + ((ILocalVariable)args.Variable).Name + " в методе " +
                        args.MethodName + "было выброшено исключение с сообщением " + args.Message;
    WriteToLog(logMessage);
};
```

***

## Работа с методами расширения Tab

Методы расширения `Tab` содержат как уникальные методы, не имеющие аналогов в `ZennoPoster`, так и обертки над стандартными методами, которые позволяют объединять методы в цепочки вызовов.

Например, вот как можно последовательно посетить два сайта используя обертки стандартных методов:

```csharp
instance.ActiveTab.Go("ya.ru").WaitLoading()
                  .Go("google.com").WaitLoading();
```

Та же логика, но без использования методов расширений:

```csharp
var tab = instance.ActiveTab;
tab.Navigate("ya.ru");
	
if(tab.IsBusy)
  tab.WaitDownloading()
	
tab.Navigate("google.com");
	
if(tab.IsBusy)
  tab.WaitDownloading()
```

### Методы `tab`.WaitFor

Методы `WaitFor` выполняют ожидание в течении указанного времени, пока не выполниться условие. 

- `WaitFor(string xpath, int number, int timeout) ` выполняет ожидание, пока на странице не будет найден Html- элемент по указанному XPath, либо до истечения таймаута.
- `WaitFor(string tags, string attrName, string attrValue, string searchKind,int number, int timeout)` выполняет ожидание, пока на странице не будет найден Html-элемент по указанном атрибутам, либо до истечения таймаута.
- `WaitFor(Func<bool> predicate, int timeout)` выполняет ожидание, пока предикат не вернет `true`, либо до истечения таймаута.

Эти методы удобны в использовании при динамическом изменении страницы, когда нужно дождаться появления элемента. 

***

## Работа с методами расширения HtmlElement

В большинстве своем методы расширения `HtmlElement` это обертки над стандартными методами, за исключением пары методов, для реализации текучего синтаксиса, как в примере ниже.

```csharp
instance.ActiveTab.GetElementByXpath("//input")
                  .ThrowIfNull("Элемент не найден")
                  .ScrollTo()
                  .Rise(Event.Focus) 
                  .ClickOn()                              
                  .AttributeSet("value", "Lorem ipsum")
                  .AttributeGet("value");
```

Как видите, здесь также, как и в локальных переменных, присутствует метод `ThrowIfXXX`.

Помимо метода `ThrowIfNull`, еще есть методы `ThrowIfHidden`, который выбрасывает исключение, если элемент скрыт и `ThrowIfNullOrHidden`, который последовательно вызывает методы `ThrowIfNull` и `ThrowIfHidden`.

