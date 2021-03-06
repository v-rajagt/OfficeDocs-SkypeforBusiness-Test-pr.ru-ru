﻿---
title: 'Lync Server 2013: диагностический отчет по одноранговой активности'
TOCTitle: Диагностический отчет по одноранговой активности
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg558602(v=OCS.15)
ms:contentKeyID: 49308759
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Диагностический отчет по одноранговой активности в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Диагностический отчет об одноранговом обмене данными предоставляет сведения об успешных и неудавшихся сеансах однорангового обмена данными. Обратите внимание на то, что в Microsoft Lync Server 2013 различаются определенные типы сбоев.

  - **Ожидаемый отказ** . Под ожидаемым отказом обычно понимается отказ в сугубо техническом смысле. Например, предположим, что вы звоните кому-то, но этого человека нет на месте, и он не может ответить на звонок. Поскольку на звонок не был получен ответ, такая ситуация технически считается отказом. С другой стороны, это был ожидаемый отказ: в Microsoft Lync Server 2013 не предполагается, что вы ответите на звонок, если вас нет на месте. Аналогичным образом, ожидаемый отказ произойдет в том случае, если вы попытаетесь отправить мгновенное сообщение пользователю, которого нет в сети или который работает с телефона, не поддерживающего обмен мгновенными сообщениями.

  - **Непредвиденный отказ** . Как следует из самого термина, непредвиденный отказ – это ошибка, которую вы не ожидаете в данных обстоятельствах. Например, предположим, что вы звоните кому-то и этот человек может ответить на звонок. Однако когда Lync Server 2013 пытается перенаправить ваш звонок на голосовую почту, происходит сбой, поскольку подключение к единой системе обмена сообщениями Exchange было утеряно. Это непредвиденная ошибка, так как звонки всегда должны иметь возможность перенаправления на голосовую почту. Как правило, непредвиденные отказы – это отказы в полном смысле слова. Это проблемы, которые обычные пользователи не могут устранить стандартными способами.

Обратите внимание на то, что число успешных сеансов, ожидаемых отказов и непредвиденных отказов может быть не равно в сумме общему числу сеансов. Например, имеются следующие значения.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Число успешных выполнений</th>
<th>Число ожидаемых сбоев</th>
<th>Число неожиданных сбоев</th>
<th>Всего сеансов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Если сложить 2024 + 469 + 16, то получится 2509 сеансов, но в столбце "Всего сеансов" показано 2521 сеансов. "Недостающие" 12 сеансов – это сеансы, которые система не смогла определить как успешные или неудавшиеся. Это иногда происходит, если в стороннем продукте используется новый код диагностики, который Lync Server не умеет обрабатывать. В этом случае звонки, совершенные с помощью этого продукта и зарегистрированные с помощью его кода диагностики, не всегда могут быть отнесены к успешным, ожидаемым отказам или непредвиденным отказам.

## Доступ к диагностическому отчету об одноранговом обмене данными

Доступ к диагностическому отчету об одноранговом обмене данными можно получить с домашней страницы "Отчеты наблюдения". Вы можете просмотреть [Отчет по распределению отказов в Lync Server 2013](lync-server-2013-failure-distribution-report.md), щелкнув один из следующих показателей:

  - Unexpected failure volume (Неожиданный сбой, объем)

  - Expected failure volume (Ожидаемый сбой, объем)

## Рекомендации по использованию диагностического отчета об одноранговом обмене данными

Имеется ряд способов фильтрации диагностического отчета об одноранговом обмене данными, но по умолчанию соответствующие параметры скрыты. Чтобы просмотреть доступные параметры фильтрации, нажмите кнопку "Показать или скрыть параметры" в правом верхнем углу окна отчета. Параметры фильтрации станут доступны для использования.

## Фильтры

Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, диагностический отчет об одноранговом обмене данными позволяет фильтровать данные по таким признакам, как модальность сеанса (например, обмен мгновенными сообщениями, передача файлов или общий доступ к приложениям). Вы также можете выбрать тип группировки данных. В этом случае звонки группируются по часам, дням или неделям.

В следующем списке перечислены фильтры, которые можно использовать с диагностическим отчетом об одноранговом обмене данными.

### Фильтры диагностического отчета об одноранговом обмене данными

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong> (От)</p></td>
<td><p>Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</p>
<p>7/7/2012 1:00 PM</p>
<p>Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Недели всегда отсчитываются с воскресенья по субботу.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong> (До)</p></td>
<td><p>Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</p>
<p>7/7/2012 1:00 PM</p>
<p>Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</p>
<p>7/7/2012</p>
<p>Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</p>
<p>7/3/2012</p>
<p>Недели всегда отсчитываются с воскресенья по субботу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong> (Интервал)</p></td>
<td><p>Временной интервал. Выберите одно из следующих значений:</p>
<ul>
<li><p>Hourly (По часам) (можно отобразить не более 25 часов)</p></li>
<li><p>Daily (По дням) (можно отобразить не более 31 дня)</p></li>
<li><p>Weekly (По неделям) (можно отобразить не более 12 недель)</p></li>
<li><p>Monthly (По месяцам) (можно отобразить не более 12 месяцев)</p></li>
</ul>
<p>Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012 по 00:00 часов 9/7/2012 (то есть всего за 31 день).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong> (Пул)</p></td>
<td><p>Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong> , чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Modality</strong> (Модальность)</p></td>
<td><p>Указывает на тип взаимодействия. Выберите один из следующих вариантов:</p>
<ul>
<li><p>[All] (Все)</p></li>
<li><p>Обмен мгновенными сообщениями</p></li>
<li><p>Передача файлов</p></li>
<li><p>Общий доступ к приложениям</p></li>
<li><p>Аудио</p></li>
<li><p>Видео</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Показатели (для каждой модальности)

В следующей таблице показаны сведения, содержащиеся в диагностическом отчете об одноранговом обмене данными для каждой модальности.

### Показатели (для каждой модальности)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Success volume</strong> (Успех, объем)</p></td>
<td><p>Нет</p></td>
<td><p>Общее количество успешных одноранговых сеансов.</p></td>
</tr>
<tr class="even">
<td><p><strong>Success percentage</strong> (Успех, процент)</p></td>
<td><p>Нет</p></td>
<td><p>Процент одноранговых сеансов, которые завершились без серьезных проблем. Вычисляется путем деления количества успешных сеансов на общее их количество.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected failure volume</strong> (Ожидаемый сбой, объем)</p></td>
<td><p>Нет</p></td>
<td><p>Общее число сеансов, в рамках которых произошли ожидаемые отказы.</p>
<p>Ожидаемый сбой ? это сбой, возникновение которого ожидаемо. Например, если пользователь задал для себя состояние «Не беспокоить», можно ожидать, что любой звонок этому пользователю будет неудачным.</p></td>
</tr>
<tr class="even">
<td><p><strong>Expected failure percentage</strong> (Ожидаемый сбой, процент)</p></td>
<td><p>Нет</p></td>
<td><p>Процент одноранговых сеансов, в рамках которых произошли ожидаемые отказы. Вычисляется путем деления количества ожидаемых отказов на общее количество сеансов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Unexpected failure volume</strong> (Неожиданный сбой, объем)</p></td>
<td><p>Нет</p></td>
<td><p>Общее число сеансов, в рамках которых произошли непредвиденные отказы.</p>
<p>Неожиданный сбой ? это событие, которое в других условиях считалось бы нормальной работой системы. Например, звонок не следует завершать, если звонящий переведен в режим удержания. Если такое произошло, данное событие будет обозначено как неожиданный сбой.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unexpected failure percentage</strong> (Неожиданный сбой, процент)</p></td>
<td><p>Нет</p></td>
<td><p>Процент одноранговых сеансов, в рамках которых произошли непредвиденные отказы. Вычисляется путем деления количества непредвиденных отказов на общее количество сеансов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Всего сеансов</strong></p></td>
<td><p>Нет</p></td>
<td><p>Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</p></td>
</tr>
</tbody>
</table>

