---
title: Документ ВСД2_Производство
tags: [formatting]
keywords: search
summary: "Документ предназначен для оформления производственной партии в системе Меркурий, как завершенной, так и незавершенной."
sidebar: mydoc_sidebar
permalink: doc_v7_production.html
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

{% include image.html file="ВСД2_Производство 7.jpg" url="images\ВСД2_Производство 7.jpg" alt="" caption="" max-width="800" %}

### Документ содержит следующее:

- Информацию о сырье, использованном для производства одной или нескольких партий продукции;
- Информацию о произведенных партиях продукции;
- Информацию о юридическом лице, которое является владельцем сырья и производит продукцию, а также информацию о месте производства;
- Идентификатор производственной операции для незавершенного производства;
- Номер производственной партии;
- Флаг завершения производственной транзакции.


### Результатом этой операции является:

- Списание нужного объема сырья из одной или нескольких записей журнала продукции;
- Добавление информации о произведенной продукции в журнал, либо присоединение к уже существующей записи, если производство не завершено;
- Для каждой добавленной записи произведенной продукции система "Меркурий" формирует ветеринарно-сопроводительный документ (ВСД), или увеличивает объем уже оформленного документа, если производство не завершено.



## **Общие сведения о сценариях**

### 1. Производство без исходного сырья

При производстве партии продукции не используется сырье. Такой сценарий возможен, если внесена информация о производстве партии живых животных, молока и т.д.

### 2. Утилизация

В данном случае указывается сырье, которое было утилизировано без указания партии продукции, произведенной из него. Такой сценарий подходит только для предприятий, которые сами утилизируют отходы. Если же отходы отправляются на утилизацию на другое предприятие, необходимо оформлять транспортный сертификат.

### 3. Сырьем для производства используется ранее выработанная партия продукции на предприятии

- Если в записи журнала указана выработанная продукция, которая была израсходована в качестве сырья, то объём продукции для записи в журнал после списания будет равен нулю.
- После этого происходит списание объёмов с указанных записей журнала.
- Запись в журнале о вырабатываемой продукции, объем которой был израсходован, переходит в статус “оформлена”.
- Затем оформляется один или несколько производственных сертификатов.
- Если были использованы производственные сертификаты, их объем гасится.
- Если выработанная продукция, указанная в записи журнала, НЕ была полностью израсходована в качестве сырья, то объём продукции, который записывается в журнал после списания, будет больше нуля.
- После этого происходит списание объёмов с указанных записей журнала.
- Затем оформляется один или несколько производственных сертификатов.

### 4. Для производства продукции используется одна или несколько партий товаров из входного журнала

Продукция, указанная в записи журнала, была полностью израсходована в качестве сырья, то есть объем продукции для записи журнала после списания стал равен нулю.

- Происходит списание объемов с указанных записей журнала.
- Запись журнала входной продукции, объем которой израсходован, переходит в статус "Оформлена".
- Оформляется один или несколько производственных сертификатов.

Если входящая продукция с указанной записи журнала НЕ была полностью израсходована, то есть объем продукции для записи журнала после списания больше нуля:

- Происходит списание объемов с указанных записей журнала.
- Оформляется один или несколько производственных сертификатов..

### 5. Незавершенное производство

При оформлении незавершенного производства можно использовать "традиционный" способ списания сырья и производства продукции в одном запросе или выпуск продукции и списание сырья отдельно. Для незавершенного производства используется понятие "производственной транзакции", которая объединяет операции списания сырья и производства продукции. В запросах указывается идентификатор транзакции в поле operationId, и пока транзакция не завершена (finalize=false), можно списывать сырье и производить продукцию. По умолчанию поле finalizeOperation = false. В запросе, выполненном в рамках производственной транзакции, должен быть хотя бы один из трех элементов:

- Списание сырья;
- Производство продукции;
- Завершение производственной транзакции (finalize=true).

### В процессе незавершенного производства происходят следующие сценарии:

- При открытии производственной транзакции происходит списание сырья в производство и создание одного или нескольких производственных сертификатов. Сертификат имеет статус "оформлен (производство не завершено)", а объемы записей журнала списываются.
- При добавлении производственной операции в транзакцию происходит списание объемов с указанных записей журнала, изменение объема в ветеринарном сертификате и увеличение объема записи произведенной продукции, если была указана произведенная продукция.
- При завершении производственной транзакции происходит списание объемов с указанных записей журнала, изменение объема в ветеринарном сертификате и увеличение объема записи произведенной продукции, если была указана произведенная продукция. Сертификат переходит в статус "Оформлен (производство завершено)".