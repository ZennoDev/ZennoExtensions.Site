---
layout: category
title: Описание методов
permalink: /docs
---

Здесь представлен список всех доступных методов библиотеки.

* [Менеджер аккаунтов](#AccountManager)
* [Настройка браузера](#BrowserManager)
* [Мультилогер](#MultiLogger)
* [Методы расширения ZennoLab.CommandCenter.Instance](#Instance)
* [Методы расширения ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel](#Project)
* [Методы расширения локальных переменных ZennoPoster](#Variables)
* [Методы расширения ZennoLab.CommandCenter.Tab](#Tab)
* [Методы расширения ZennoLab.CommandCenter.HtmlElement](#HtmlElement)
* [Методы расширения DateTime](#DateTime)
* [Методы расширения для Integer](#Int32)

***

<a name="AccountManager"></a>
## Менеджер аккаунтов
Функционал многопоточной работы со списком аккаунтов.

Метод | Описание
------------ | -------------
[GetInstance]({{ site.url }}/docs/AccountManager/GetInstance/) | Возвращает экземпляр класса AccountManager.
[Initialize]({{ site.url }}/docs/AccountManager/Initialize/) | Производит инициализацию менеджера аккаунтов.Сопоставляет существующую конфигурацию аккаунтов или создает новую для файла с аккаунтами.
[GetFreeAccountWithMinExecutionsCount]({{ site.url }}/docs/AccountManager/GetFreeAccountWithMinExecutionsCount/) | Возвращает свободный аккаунт с наименьшим количеством запусков.
[GetAccount]({{ site.url }}/docs/AccountManager/GetAccount/) | Возвращает аккаунт, удовлетворяющий предикату.
[ReleaseAccounts]({{ site.url }}/docs/AccountManager/ReleaseAccounts/) | Освобождает все аккаунты для которых предикат возвращает true.

***

<a name="BrowserManager"></a>
## Менеджер браузера
Гибкая генерация свойств навигатора, UserAgent'а, отпечатков и множества других параметров.

Метод | Описание
------------ | -------------
[BrowserManager.Generate]({{ site.url }}/docs/BrowserManager/Generate/) | Генерация профиля браузера.
[BrowserManager.Setup]({{ site.url }}/docs/BrowserManager/Setup/) | Применяет конфигурацию к ZennoPoster&lsquo;y.
[BrowserManager.Save]({{ site.url }}/docs/BrowserManager/Save/) | Сериализует и сохраняет объект профиля браузера.
[BrowserManager.Load]({{ site.url }}/docs/BrowserManager/Load/) | Загружает объект профиля браузера, сохраненный в файл.
[BrowserManager.LoadFromString]({{ site.url }}/docs/BrowserManager/LoadFromString/) | Загружает объект профиля браузера, сохраненный в строку.

***

<a name="MultiLogger"></a>
## Мультилогер
Возможность одновременного логирования в несколько источников.

Метод | Описание
------------ | -------------
[GetInstance]({{ site.url }}/docs/MultiLogger/GetInstance/) | Возвращает экземпляр класса MultiLogger.
[MultiLog]({{ site.url }}/docs/MultiLogger/MultiLog/) | Логирование через набор логгеров, установленных через свойство LogTo.
[MultiLogDebug]({{ site.url }}/docs/MultiLogger/MultiLogDebug/) | Логирование в режиме Debug через набор логгеров, установленных через свойство LogTo.
[LogToProjectMaker]({{ site.url }}/docs/MultiLogger/LogToProjectMaker/) | Вывод сообщения в лог ProjectMaker.Обертка над методами project.Send***ToLog.
[LogToProjectMakerDebug]({{ site.url }}/docs/MultiLogger/LogToProjectMakerDebug/) | Вывод сообщения в лог ProjectMaker в режиме Debug.Обертка над методами project.Send***ToLog.
[LogToFile]({{ site.url }}/docs/MultiLogger/LogToFile/) | Логирование в файл.
[LogToFileDebug]({{ site.url }}/docs/MultiLogger/LogToFileDebug/) | Логирование в файл в режиме Debug.
[LogByCustom]({{ site.url }}/docs/MultiLogger/LogByCustom/) | Логирование через набор пользовательских логгеров, установленных в свойстве CustomLoggers.
[LogByCustomDebug]({{ site.url }}/docs/MultiLogger/LogByCustomDebug/) | Логирование в режиме Debug через набор пользовательских логгеров, установленных в свойстве CustomLoggers.

***

<a name="Instance"></a>
## Методы расширения для ZennoLab.CommandCenter.Instance
Дополнительный функционал для работы с инстансом.

Метод | Описание
------------ | -------------
[instance.ClearCacheAndCookie]({{ site.url }}/docs/Instance/ClearCacheAndCookie/) | Очищает кэш и куки

***

<a name="Project"></a>
## Методы расширения для ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel
Дополнительный функционал для работы с project'ом.

Метод | Описание
------------ | -------------
[project.GetLogger]({{ site.url }}/docs/Project/GetLogger/) | Возвращает объект мультилоггера.

***

<a name="Variables"></a>
## Методы расширения локальных переменных ZennoPoster
Дополнительный функционал для работы с локальными переменными project.Variables["name"].

Метод | Описание
------------ | -------------
[IsEmpty]({{ site.url }}/docs/Variables/IsEmpty/) | Проверяет указано ли значение переменной.
[IsInt]({{ site.url }}/docs/Variables/IsInt/) | Проверяет является ли значение переменной целым числом.
[IsDouble]({{ site.url }}/docs/Variables/IsDouble/) | Проверяет является ли значение переменной вещественным числом.
[IsBool]({{ site.url }}/docs/Variables/IsBool/) | Проверяет является ли значение переменной логическим значением.
[IsDate]({{ site.url }}/docs/Variables/IsDate/) | Проверяет является ли значение переменной датой.
[IsFileExists]({{ site.url }}/docs/Variables/IsFileExists/) | Проверяет существует ли файл по указанному пути.
[IsTextFileEmpty]({{ site.url }}/docs/Variables/IsTextFileEmpty/) | Проверяет пуст ли текстовый файл.
[IsDirectoryExists]({{ site.url }}/docs/Variables/IsDirectoryExists/) | Проверяет существует ли директория по указанному пути.
[IsDirectoryEmpty]({{ site.url }}/docs/Variables/IsDirectoryEmpty/) | Проверяет есть ли файлы в директории.
[IsArray]({{ site.url }}/docs/Variables/IsArray/) | Проверяет является ли строка массивом данных.
[IsRange]({{ site.url }}/docs/Variables/IsRange/) | Проверяет является ли значение переменной диапазоном чисел или дат.
[ToRangeOfFloatNumbers]({{ site.url }}/docs/Variables/ToRangeOfFloatNumbers/) | Конвертирует строковое значение переменной в диапазон вещественных чисел.
[ToRangeOfNumbers]({{ site.url }}/docs/Variables/ToRangeOfNumbers/) | Конвертирует строковое значение переменной в диапазон целых чисел.
[ToRangeOfDates]({{ site.url }}/docs/Variables/ToRangeOfDates/) | Конвертирует строковое значение переменной в диапазон дат.
[ToBool]({{ site.url }}/docs/Variables/ToBool/) | Конвертирует строковое значение переменной в Boolean.
[ToInt]({{ site.url }}/docs/Variables/ToInt/) | Конвертирует строковое значение переменной в Int32.
[ToDouble]({{ site.url }}/docs/Variables/ToDouble/) | Конвертирует строковое значение переменной в Double.
[ToDateTime]({{ site.url }}/docs/Variables/ToDateTime/) | Конвертирует строковое значение переменной в DateTime.
[ToArray]({{ site.url }}/docs/Variables/ToArray/) | Разбивает строковое значение переменной на массив значений.
[Spintax]({{ site.url }}/docs/Variables/Spintax/) | Применяет Spintax к содержимому переменной.
[ThrowIfEmpty]({{ site.url }}/docs/Variables/ThrowIfEmpty/) | Бросает исключение, если переменная пустая.
[ThrowIfNotInt]({{ site.url }}/docs/Variables/ThrowIfNotInt/) | Бросает исключение, если значение переменной не является целым числом.
[ThrowIfNotBool]({{ site.url }}/docs/Variables/ThrowIfNotBool/) | Бросает исключение, если значение переменной не является логическим значением.
[ThrowIfNotDouble]({{ site.url }}/docs/Variables/ThrowIfNotDouble/) | Бросает исключение, если значение переменной не является вещественным числом.
[ThrowIfNotDate]({{ site.url }}/docs/Variables/ThrowIfNotDate/) | Бросает исключение, если значение переменной не является датой.
[ThrowIfNotArray]({{ site.url }}/docs/Variables/ThrowIfNotArray/) | Бросает исключение, если значение переменной не является массивом данных.
[ThrowIfFileNotExists]({{ site.url }}/docs/Variables/ThrowIfFileNotExists/) | Бросает исключение, если файл не существует по указанному пути.
[ThrowIfTextFileIsEmpty]({{ site.url }}/docs/Variables/ThrowIfTextFileIsEmpty/) | Бросает исключение, если файл пуст.
[ThrowIfDirectoryNotExists]({{ site.url }}/docs/Variables/ThrowIfDirectoryNotExists/) | Бросает исключение, если директория не существует по указанному пути.
[ThrowIfDirectoryIsEmpty]({{ site.url }}/docs/Variables/ThrowIfDirectoryIsEmpty/) | Бросает исключение, если директория пуста.
[ThrowIfNotRange]({{ site.url }}/docs/Variables/ThrowIfNotRange/) | Бросает исключение, если значение переменной не является диапазоном.

***

<a name="Tab"></a>
## Методы расширения ZennoLab.CommandCenter.Tab
Дополнительный функционал для работы с табом.

Метод | Описание
------------ | -------------
[tab.Go]({{ site.url }}/docs/Tab/Go/) | Выполняет переход по указанному Url. Обертка над Navigate.
[tab.Refresh]({{ site.url }}/docs/Tab/Refresh/) | Выполняет обновление текущей страницы.
[tab.WaitLoading]({{ site.url }}/docs/Tab/WaitLoading/) | Выполняет ожидание полной прогрузки страницы.
[tab.GetElementByXpath]({{ site.url }}/docs/Tab/GetElementByXpath/) | Находит элемент по XPath. Обертка над FindElementByXPath.
[tab.WaitFor]({{ site.url }}/docs/Tab/WaitFor/) | Выполняет ожидание, пока на странице не будет выполнено условие.

***

<a name="HtmlElement"></a>
## Методы расширения для ZennoLab.CommandCenter.HtmlElement
Дополнительный функционал для работы с элементами страницы.

Метод | Описание
------------ | -------------
[element.IsHidden]({{ site.url }}/docs/HtmlElement/IsHidden/) | Проверяет скрыт ли элемент.
[element.Rise]({{ site.url }}/docs/HtmlElement/Rise/) | Выполняет событие для элемента.
[element.ClickOn]({{ site.url }}/docs/HtmlElement/ClickOn/) | Выполняет клик по элементу.
[element.SetAttr]({{ site.url }}/docs/HtmlElement/SetAttr/) | Устанавливает значение атрибуа элемента.
[element.GetAttr]({{ site.url }}/docs/HtmlElement/GetAttr/) | Получает значение атрибуа элемента.
[element.SetVal]({{ site.url }}/docs/HtmlElement/SetVal/) | Устанавливает значение элемента.
[element.GetVal]({{ site.url }}/docs/HtmlElement/GetVal/) | Возвращает значение элемента. Обертка над GetValue();
[element.ScrollTo]({{ site.url }}/docs/HtmlElement/ScrollTo/) | Прокручивает страницу к текущему элементу. Обертка над ScrollIntoView().
[element.ThrowIfNull]({{ site.url }}/docs/HtmlElement/ThrowIfNull/) | Бросает исключение, если элемент пуст (свойство IsVoid возвращает true).
[element.ThrowIfHidden]({{ site.url }}/docs/HtmlElement/ThrowIfHidden/) | Бросает исключение, если елемент скрыт.
[element.ThrowIfNullOrHidden]({{ site.url }}/docs/HtmlElement/ThrowIfNullOrHidden/) | Бросает исключение, если елемент пуст (свойство IsVoid возвращает true) или скрыт.

***

<a name="DateTime"></a>
## Методы расширения DateTime


Метод | Описание
------------ | -------------
[date.ToUnixTime]({{ site.url }}/docs/DateTime/ToUnixTime/) | Конвертирует дату в число в формате UnixTime.

***

<a name="Int32"></a>
## Методы расширения для Integer


Метод | Описание
------------ | -------------
[number.UnixTimeToDateTime]({{ site.url }}/docs/Int32/UnixTimeToDateTime/) | Конвертирует число представляющее UnixTime в соответствующую дату в формате DateTime.

***

