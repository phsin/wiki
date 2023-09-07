---
title: Настройка параметров в 1С 8
tags: [formatting]
keywords: search
#summary: "Документ предназначен для оформления в системе Меркурий транспортной партии."
sidebar: mydoc_sidebar
permalink: vsd_params_v8.html
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

Для интеграции данных с ФГИС "Меркурий" в 1С:Предприятие 8 необходимо выбрать соответствующие параметры.

• Для этого перейдите на вкладку **"КБ99"** → **"Сервис"** → **"Параметры интеграции"**.

{% include image.html file="Настройка параметров в 1С 8 1.jpg" url="images\Настройка параметров в 1С 8 1.jpg" alt="" caption="" max-width="800" %}

• Укажите реквизиты для подключения к Ветис.API и реквизиты для входа на сайт "Меркурий".


{% include note.html content="Код лицензии заполняется только для продуктивного контура. Для тестовой версии заполнение не требуется." %}

• Нажмите кнопку **"Выполнить"**, чтобы выполнить начальную загрузку данных.

{% include image.html file="Настройка параметров в 1С 8 2.jpg" url="images\Настройка параметров в 1С 8 2.jpg" alt="" caption="" max-width="800" %}

• Заполните параметры **по умолчанию**.

{% include image.html file="Настройка параметров в 1С 8 3.jpg" url="images\Настройка параметров в 1С 8 3.jpg" alt="" caption="" max-width="800" %}

• Заполните данные на вкладке **"Документы"**.

{% include image.html file="Настройка параметров в 1С 8 4.jpg" url="images\Настройка параметров в 1С 8 4.jpg" alt="" caption="" max-width="800" %}

• Перейдите на вкладку **"Интеграция ФГИС Ветис"** и загрузите партии.

{% include image.html file="Настройка параметров в 1С 8 5.jpg" url="images\Настройка параметров в 1С 8 5.jpg" alt="" caption="" max-width="800" %}

{% include image.html file="Настройка параметров в 1С 8 6.jpg" url="images\Настройка параметров в 1С 8 6.jpg" alt="" caption="" max-width="800" %}


Партии успешно загружены.

Установка завершена. Теперь вы можете перейти к следующему шагу - [установке соответствия площадок](http://wiki.kb99.pro/vsd_ploschadki_v8.html).