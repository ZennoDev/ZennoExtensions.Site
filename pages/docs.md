---
layout: category
title: Документация
permalink: /docs
---

Здесь представлен список всех доступных методов библиотеки.

* [Менеджер аккаунтов](#AccountManager)
* [Настройка браузера](#Browser)
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
[GetInstance](/docs/AccountManager/GetInstance/) | Возвращает экземпляр класса AccountManager.
[Initialize](/docs/AccountManager/Initialize/) | Производит инициализацию менеджера аккаунтов.Сопоставляет существующую конфигурацию аккаунтов или создает новую для файла с аккаунтами.
[GetFreeAccountWithMinExecutionsCount](/docs/AccountManager/GetFreeAccountWithMinExecutionsCount/) | Возвращает свободный аккаунт с наименьшим количеством запусков.
[GetAccount](/docs/AccountManager/GetAccount/) | Возвращает аккаунт, удовлетворяющий предикату.
[ReleaseAccounts](/docs/AccountManager/ReleaseAccounts/) | Освобождает все аккаунты для которых предикат возвращает true.

***

<a name="Browser"></a>
## Настройка браузера
Гибкая генерация свойств навигатора, UserAgent'а, отпечатков и множества других параметров.

Метод | Описание
------------ | -------------
[BrowserManager.Generate](/docs/Browser/Generate/) | Генерация профиля браузера.
[BrowserManager.Setup](/docs/Browser/Setup/) | Применяет конфигурацию к ZennoPoster&lsquo;y.
[BrowserManager.Save](/docs/Browser/Save/) | Сериализует и сохраняет объект профиля браузера.
[BrowserManager.Load](/docs/Browser/Load/) | Загружает объект профиля браузера, сохраненный в файл.
[BrowserManager.LoadFromString](/docs/Browser/LoadFromString/) | Загружает объект профиля браузера, сохраненный в строку.

***

<a name="MultiLogger"></a>
## Мультилогер
Возможность одновременного логирования в несколько источников.

Метод | Описание
------------ | -------------
[GetInstance](/docs/MultiLogger/GetInstance/) | Возвращает экземпляр класса MultiLogger.
[MultiLog](/docs/MultiLogger/MultiLog/) | Логирование через набор логгеров, установленных через свойство LogTo.
[LogToProjectMaker](/docs/MultiLogger/LogToProjectMaker/) | Вывод сообщения в лог ProjectMaker.Обертка над методами project.Send***ToLog.
[LogToFile](/docs/MultiLogger/LogToFile/) | Логирование в файл.
[LogByCustom](/docs/MultiLogger/LogByCustom/) | Логирование через набор пользовательских логгеров, установленных в свойстве CustomLoggers.

***

<a name="Instance"></a>
## Методы расширения для ZennoLab.CommandCenter.Instance
Дополнительный функционал для работы с инстансом.

Метод | Описание
------------ | -------------
[instance.ClearCacheAndCookie](/docs/Instance/ClearCacheAndCookie/) | Очищает кэш и куки

***

<a name="Project"></a>
## Методы расширения для ZennoLab.InterfacesLibrary.ProjectModel.IZennoPosterProjectModel
Дополнительный функционал для работы с project'ом.

Метод | Описание
------------ | -------------
[project.GetLogger](/docs/Project/GetLogger/) | Возвращает объект мультилоггера.

***

<a name="Variables"></a>
## Методы расширения локальных переменных ZennoPoster
Дополнительный функционал для работы с локальными переменными project.Variables["name"].

Метод | Описание
------------ | -------------
[IsEmpty](/docs/Variables/IsEmpty/) | Проверяет указано ли значение переменной.
[IsInt](/docs/Variables/IsInt/) | Проверяет является ли значение переменной целым числом.
[IsDouble](/docs/Variables/IsDouble/) | Проверяет является ли значение переменной вещественным числом.
[IsBool](/docs/Variables/IsBool/) | Проверяет является ли значение переменной логическим значением.
[IsDate](/docs/Variables/IsDate/) | Проверяет является ли значение переменной датой.
[IsFileExists](/docs/Variables/IsFileExists/) | Проверяет существует ли файл по указанному пути.
[IsTextFileEmpty](/docs/Variables/IsTextFileEmpty/) | Проверяет пуст ли текстовый файл.
[IsDirectoryExists](/docs/Variables/IsDirectoryExists/) | Проверяет существует ли директория по указанному пути.
[IsDirectoryEmpty](/docs/Variables/IsDirectoryEmpty/) | Проверяет есть ли файлы в директории.
[IsArray](/docs/Variables/IsArray/) | Проверяет является ли строка массивом данных.
[IsRange](/docs/Variables/IsRange/) | Проверяет является ли значение переменной диапазоном чисел или дат.
[ToRangeOfFloatNumbers](/docs/Variables/ToRangeOfFloatNumbers/) | Конвертирует строковое значение переменной в диапазон вещественных чисел.
[ToRangeOfNumbers](/docs/Variables/ToRangeOfNumbers/) | Конвертирует строковое значение переменной в диапазон целых чисел.
[ToRangeOfDates](/docs/Variables/ToRangeOfDates/) | Конвертирует строковое значение переменной в диапазон дат.
[ToBool](/docs/Variables/ToBool/) | Конвертирует строковое значение переменной в Boolean.
[ToInt](/docs/Variables/ToInt/) | Конвертирует строковое значение переменной в Int32.
[ToDouble](/docs/Variables/ToDouble/) | Конвертирует строковое значение переменной в Double.
[ToDateTime](/docs/Variables/ToDateTime/) | Конвертирует строковое значение переменной в DateTime.
[ToArray](/docs/Variables/ToArray/) | Разбивает строковое значение переменной на массив значений.
[Spintax](/docs/Variables/Spintax/) | Применяет Spintax к содержимому переменной.
[ThrowIfEmpty](/docs/Variables/ThrowIfEmpty/) | Бросает исключение, если переменная пустая.
[ThrowIfNotInt](/docs/Variables/ThrowIfNotInt/) | Бросает исключение, если значение переменной не является целым числом.
[ThrowIfNotBool](/docs/Variables/ThrowIfNotBool/) | Бросает исключение, если значение переменной не является логическим значением.
[ThrowIfNotDouble](/docs/Variables/ThrowIfNotDouble/) | Бросает исключение, если значение переменной не является вещественным числом.
[ThrowIfNotDate](/docs/Variables/ThrowIfNotDate/) | Бросает исключение, если значение переменной не является датой.
[ThrowIfNotArray](/docs/Variables/ThrowIfNotArray/) | Бросает исключение, если значение переменной не является массивом данных.
[ThrowIfFileNotExists](/docs/Variables/ThrowIfFileNotExists/) | Бросает исключение, если файл не существует по указанному пути.
[ThrowIfTextFileIsEmpty](/docs/Variables/ThrowIfTextFileIsEmpty/) | Бросает исключение, если файл пуст.
[ThrowIfDirectoryNotExists](/docs/Variables/ThrowIfDirectoryNotExists/) | Бросает исключение, если директория не существует по указанному пути.
[ThrowIfDirectoryIsEmpty](/docs/Variables/ThrowIfDirectoryIsEmpty/) | Бросает исключение, если директория пуста.
[ThrowIfNotRange](/docs/Variables/ThrowIfNotRange/) | Бросает исключение, если значение переменной не является диапазоном.

***

<a name="Tab"></a>
## Методы расширения ZennoLab.CommandCenter.Tab
Дополнительный функционал для работы с табом.

Метод | Описание
------------ | -------------
[tab.Go](/docs/Tab/Go/) | Выполняет переход по указанному Url. Обертка над Navigate.
[tab.Refresh](/docs/Tab/Refresh/) | Выполняет обновление текущей страницы.
[tab.WaitLoading](/docs/Tab/WaitLoading/) | Выполняет ожидание полной прогрузки страницы.
[tab.GetElementByXpath](/docs/Tab/GetElementByXpath/) | Находит элемент по XPath. Обертка над FindElementByXPath.
[tab.WaitFor](/docs/Tab/WaitFor/) | Выполняет ожидание, пока на странице не будет выполнено условие.

***

<a name="HtmlElement"></a>
## Методы расширения для ZennoLab.CommandCenter.HtmlElement
Дополнительный функционал для работы с элементами страницы.

Метод | Описание
------------ | -------------
[element.IsHidden](/docs/HtmlElement/IsHidden/) | Проверяет скрыт ли элемент.
[element.Rise](/docs/HtmlElement/Rise/) | Выполняет событие для элемента.
[element.ClickOn](/docs/HtmlElement/ClickOn/) | Выполняет клик по элементу.
[element.AttributeSet](/docs/HtmlElement/AttributeSet/) | Устанавливает значение атрибуа элемента.
[element.AttributeGet](/docs/HtmlElement/AttributeGet/) | Получает значение атрибуа элемента.
[element.ValueSet](/docs/HtmlElement/ValueSet/) | Устанавливает значение элемента.
[element.ValueGet](/docs/HtmlElement/ValueGet/) | Возвращает значение элемента. Обертка над GetValue();
[element.ScrollTo](/docs/HtmlElement/ScrollTo/) | Прокручивает струницу к текущему элементу. Обертка над ScrollIntoView().
[element.ThrowIfNull](/docs/HtmlElement/ThrowIfNull/) | Бросает исключение, если элемент пуст (свойство IsVoid возвращает true).
[element.ThrowIfHidden](/docs/HtmlElement/ThrowIfHidden/) | Бросает исключение, если елемент скрыт.
[element.ThrowIfNullOrHidden](/docs/HtmlElement/ThrowIfNullOrHidden/) | Бросает исключение, если елемент пуст (свойство IsVoid возвращает true) или скрыт.

***

<a name="DateTime"></a>
## Методы расширения DateTime


Метод | Описание
------------ | -------------
[date.ToUnixTime](/docs/DateTime/ToUnixTime/) | Конвертирует дату в число в формате UnixTime.

***

<a name="Int32"></a>
## Методы расширения для Integer


Метод | Описание
------------ | -------------
[number.UnixTimeToDateTime](/docs/Int32/UnixTimeToDateTime/) | Конвертирует число представляющее UnixTime в соответствующую дату в формате DateTime.

***

