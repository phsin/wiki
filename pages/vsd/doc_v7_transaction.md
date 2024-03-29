---
title: Документ ВСД2_Транзакция
tags: [formatting]
keywords: search
summary: "Предназначен для оформления транспортной партии в системе Меркурий."
sidebar: mydoc_sidebar
permalink: doc_v7_transaction.html
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


{% include image.html file="ВСД2_Транзакция 1 новый.jpg" url="images\ВСД2_Транзакция 1 новый.jpg" alt="" caption="" max-width="800" %}

### Параметры

Данный документ содержит следующую информацию:

- Информацию об одной или нескольких партиях продукции, из которых будет сформирована транспортная партия;
- Сведения о получателе транспортной партии;
- Сведения о транспортном средстве и маршруте его следования;
- Дополнительные сведения, необходимые для оформления ветеринарно-сопроводительного документа (ВСД), такие как результаты ветеринарно-санитарной экспертизы, сведения о ТТН, особые отметки и т.д.

### Результат

- Осуществляется списание объема с одной или нескольких записей журнала продукции, указанных в заявке.
- Производственный сертификат гасится, если был указан весь объем по данной записи журнала вырабатываемой продукции.
- Для каждого наименования продукции, указанного в транспортной партии, система "Меркурий" формирует ветеринарно-сопроводительный документ (ВСД).

### Сценарии

При выполнении операции могут возникнуть следующие сценарии:

- Перевозка со сменой владельца: в сведениях об отправителе и получателе указаны разные хоз. субъекты и предприятия.
- Перевозка без смены владельца: в сведениях об отправителе и получателе указан один и тот же хоз. субъект, но разные предприятия.
- Смена владельца без перевозки: в сведениях об отправителе и получателе указаны разные хоз. субъекты, но одинаковые предприятия.

Для записей журнала возможны следующие ситуации:

1. Продукция из записи журнала была полностью израсходована (отгружена), то есть объем продукции после списания стал равен нулю. Происходит списание объемов с одной или нескольких записей журнала. Одна или несколько записей журнала вырабатываемой продукции, объем которых израсходован, переходит в категорию «Оформленных». Оформляется ВСД на каждое наименование отгружаемой продукции. Происходит гашение производственных сертификатов, объем которых был израсходован.
2. Продукция из записи журнала не была полностью израсходована, то есть объем продукции для записи журнала после списания больше нуля. Происходит списание объемов с одной или нескольких записей журнала. Оформляется ВСД на каждое наименование отгружаемой продукции.

При перемещении между площадками вы можете гасить (подтверждать получение) сразу из документа ВСД2_транзакция, без получения списка партий по Площадке_Получателю.

## **Видео: Оформление ВСД транзакции Ветис 2.0**

<iframe width="854" height="480" src="https://www.youtube.com/embed/SOZu23Wwd1I?autoplay=1&rel=0" frameborder="0" allowfullscreen></iframe>


## **Вебинар Оформление входящих ВСД, лабораторных исследований и транспортных ВСД [26.02.2018]**

<iframe width="854" height="480" src="https://www.youtube.com/embed/AOomC2Lp_kE?rel=0" frameborder="0" allowfullscreen></iframe>


## **Видео: Смена владельца партий без перевозки**

Перемещаем партии из одной фирмы в другую в одной базе 1С

<iframe width="854" height="480" src="https://www.youtube.com/embed/Uw01YRLqdL8?rel=0" frameborder="0" allowfullscreen></iframe>