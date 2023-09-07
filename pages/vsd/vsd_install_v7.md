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

{% include important.html content="Перед установкой необходимо создать резервную копию вашей конфигурации и всех обработок." %}

Рекомендуется устанавливать модуль на копию вашей рабочей базы данных. После проверки всех функций и операций вы можете перенести изменения из тестовой версии в рабочую.

Для установки модуля выполните следующие шаги:

• Скачайте последнюю версию модуля из [продуктивного проекта](https://redmine.kb99.pro/projects/vsd_1c_work/files).

• Скопируйте все обработки ert из архива `zip:\\\\Vetis` в каталог `каталогИБ\\\\Vetis`, заменив любые существующие файлы.

**Примечание:** Единственным исключением является обработка `Меркурий_Интеграция.ert`, которая содержит переопределения стандартных функций модуля интеграции для вашей конфигурации.

• Объедините вашу конфигурацию с конфигурацией из архива `1cv7_Vetis.md`.

{% include important.html content="Добавляйте только новые объекты. Для изменений в существующих справочниках и документах следует использовать ручной перенос." %}

{% include image.html file="Установка в 1С Предприятие 7.7.png" url="images\Установка в 1С Предприятие 7.7.png" alt="Установка модуля интеграции в конфигурацию 1С Торговля и склад" caption="Установка модуля интеграции в конфигурацию 1С Торговля и склад" %}

1. <span class="glyphicon glyphicon-download"></span> Добавьте в *Глобальный модуль* вашей конфигурации из MD
* В процедуру *ПриНачалеРаботыСистемы();
* Глобальные переменные.

2. <span class="glyphicon glyphicon-download"></span> Добавьте кнопку _ВСД_ на форму и процедуру _ДействияВСД()_ в модуль документов
* Реализация;
* Поступление;
* Перемещение.

3. <span class="glyphicon glyphicon-download"></span> Установите [Microsoft .NET Framework 4](https://www.microsoft.com/ru-RU/download/details.aspx?id=17718)

4. <span class="glyphicon glyphicon-download"></span> Скопируйте библиотеки dll из  каталога `Vetis` в `каталогИБ`
* 1cpp.dll версия 3.2.4.3;
* 1sqlite.dll версия 1.0.2.3;
* FormEx.dll версия 2.0.5.0;
* SoapDLL_test.dll.

{% include note.html content="Если у вас установлены 1cpp.dll или formex.dll, проверьте, чтобы версии установленных библиотек были больше указанных версий." %}

* Проверьте пути к классам в файле [defcls.prm](https://github.com/phsin/vetrf/blob/master/defcls.prm)
* Зарегистрируйте soapdll_test.dll - запустите файл [reg_test.bat](https://github.com/phsin/vetrf/blob/master/Vetis/reg_test.bat) в каталоге `Vetis`

Установка завершена. Можете переходить к следующему шагу - [Настройка параметров](vsd_params_v7.html)
