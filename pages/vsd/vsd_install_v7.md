---
title: Установка модуля интеграции в 1С 7.7
tags: [formatting]
keywords: search
#summary: "Документ предназначен для оформления в системе Меркурий транспортной партии."
sidebar: mydoc_sidebar
permalink: vsd_install_v7.html
folder: vsd
toc: false
tags: false
---

<style>
.result {
background-color: #000000;
border: 1px solid #dedede;
padding: 10px;
margin-top: 10px;
margin-bottom: 10px;
}
</style>

{% include important.html content="Сделайте архивную копию конфигурации и всех обработок." %}

Устанавливать рекомендуется на копию рабочей ИБ, после проверки всех функций и операций - переносить изменения из тестовой версий в рабочую.

* Скачайте последнюю версию модуля из [продуктивного проекта](https://redmine.kb99.pro/projects/vsd_1c/files)
* Скопируйте с заменой все обработки ert из архива `zip:\Vetis` в каталог `каталогИБ \ Vetis`

{% include note.html content="кроме Меркурий_Интеграция.ert - в этой обработке хранятся переопределения стандартных функций модуля интеграции для вашей конфигурации" %}

* Объедините вашу конфигурацию с конфигурацией из архива  `1cv7_Vetis.md`

{% include important.html content="Добавляйте только новые объекты. В существующие справочники и документы изменения переносите вручную." %}

{% include image.html file="screenshot_1_1563538797_2019-07-19_16-18-28.png" url="" alt="Установка модуля интеграции в конфигурацию 1С Торговля и склад" caption="Установка модуля интеграции в конфигурацию 1С Торговля и склад" %}

<span class="glyphicon glyphicon-download"></span> Добавьте в *Глобальный модуль* вашей конфигурации из MD
* в процедуру *ПриНачалеРаботыСистемы()
* глобальные переменные

<span class="glyphicon glyphicon-download"></span> Добавьте кнопку _ВСД_ на форму и процедуру _ДействияВСД()_ в модуль документов
* Реализация
* Поступление
* Перемещение

<span class="glyphicon glyphicon-download"></span> Установите [Microsoft .NET Framework 4](https://www.microsoft.com/ru-RU/download/details.aspx?id=17718)

<span class="glyphicon glyphicon-download"></span> Скопируйте библиотеки dll из  каталога `Vetis` в `каталогИБ`
* 1cpp.dll версия 3.2.4.3
* 1sqlite.dll версия 1.0.2.3
* FormEx.dll версия 2.0.5.0
* SoapDLL_test.dll 

{% include note.html content="Если у вас установлены 1cpp.dll или formex.dll проверьте, чтобы версии установленных библиотек были больше указанных версий." %}

* Проверьте пути к классам в файле [defcls.prm](https://github.com/phsin/vetrf/blob/master/defcls.prm)
* Зарегистрируйте soapdll_test.dll - запустите файл [reg_test.bat](https://github.com/phsin/vetrf/blob/master/Vetis/reg_test.bat) в каталоге `Vetis`

Установка завершена. Можете переходить к следующему шагу - [Настройка параметров](vsd_params_v7.html)
