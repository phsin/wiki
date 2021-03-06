---
title: Установка модуля интеграции в 1С 8
tags: [formatting]
keywords: search
summary: "Установка модуля интеграции в конфигурацию с управляемыми формами"
sidebar: mydoc_sidebar
permalink: vsd_install_v8_3.html
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


{% include important.html content="Сделайте архивную копию конфигурации." %}

Интеграцию можно использовать 
* установить в отдельной конфигурации,
* объединить с рабочей конфигурацией, при этом больше функций по формированию документов из документов.

Объединение интеграции с рабочей конфигурацией рекомендуем выполнять в следуюзем порядке:

1. Скачать [продуктивную версию интеграции](https://redmine.kb99.pro/projects/vsd_1c/files)
2. Сравнить и объединить с конфигурацией из файла

{% include image.html file="screenshot_1_1553001606_2019-03-19_17-17-15.png" url="" alt="Убрать все галки" caption="Убрать все галки" %}

{% include image.html file="screenshot_2_1553001634_2019-03-19_17-15-01.png" url="" alt="Отметить по подсистемам файла - отметить ВСД" caption="Отметить по подсистемам файла - отметить ВСД" %}

{% include image.html file="screenshot_3_1553001639_2019-03-19_17-15-50.png" url="" alt="Выбрать подсистему ВСД" caption="Выбрать подсистему ВСД" %}

{% include image.html file="screenshot_4_1553001651_2019-03-19_17-16-28__2_.png" url="" alt="Объединить конфигурации - нажать на кнопку Выполнить" caption="Объединить конфигурации - нажать на кнопку Выполнить" %}

* (не обязательно) В конфигурации *добавить документы ВСД* в 
* * Критерии отбора - Связанные документы 
* * Общие команды - Структура подчиненности.

{% include tip.html content="Рекомендуется использовать последнюю версию платформы, больше 8.3.14" %}

Установка завершена. Можете переходить к следующему шагу - [Настройка параметров](vsd_params_v8.html)
