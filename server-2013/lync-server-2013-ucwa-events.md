﻿---
title: События UCWA
TOCTitle: События UCWA
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945621(v=OCS.15)
ms:contentKeyID: 52058177
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# События UCWA

 

_**Дата изменения раздела:** 2015-03-09_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 использует веб-интерфейс API объединенных коммуникаций (UCWA) для выполнения разных задач от доступа к Microsoft Exchange для поиска контактов до обновления сведений о присутствии для мобильных клиентов.

UCWA занесет записи о рабочем поведении с типами событий "Информационный", "Предупреждение" и "Ошибка". В следующей таблице описываются события, которые могут регистрироваться компонентами UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Идентификатор события</th>
<th>Тип события</th>
<th>Сводка</th>
<th>Причина и решение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Информационный</p></td>
<td><p>Инициализировано UCWA</p></td>
<td><p>Н/Д</p>
<p>Н/Д</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Ошибка</p></td>
<td><p>Во время инициализации UCWA возникло неожиданное исключение</p></td>
<td><p>Во время инициализации возникла неожиданная ошибка</p>
<p>Изучите сведения об исключении в соответствующей записи журнала событий, чтобы определить возможную причину</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Ошибка</p></td>
<td><p>В UCWA возникло необработанное исключение</p></td>
<td><p>Возникло необработанное исключение</p>
<p>Перезапустите сервер. Если проблема не устранена, обратитесь в службу поддержки продукта.</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается получить доступ к Exchange для фотографии с высоким разрешением</p></td>
<td><p>Недоступно подключение к Exchange</p>
<p>Убедитесь в доступности соединения с Exchange</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя доступа к Exchange для фотографии с высоким разрешением</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается получить доступ к Exchange для поиска контакта</p></td>
<td><p>Недоступно подключение к Exchange</p>
<p>Убедитесь в доступности соединения с Exchange</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя поиска контакта в Exchange</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Предупреждение</p></td>
<td><p>Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</p></td>
<td><p>Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</p>
<p>Проверьте клиенты на наличие лишних подписок</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Предупреждение</p></td>
<td><p>Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</p></td>
<td><p>Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</p>
<p>Проверьте клиенты на наличие лишних подписок</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается получить внутриполосные данные</p></td>
<td><p>Не удается получить внутриполосные данные</p>
<p>Если проблема не устранена, обратитесь в службу поддержки продукта.</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается подписаться на сведения о присутствии</p></td>
<td><p>Не удается подписаться на сведения о присутствии</p>
<p>Если проблема не устранена, обратитесь в службу поддержки продукта.</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удалось зарегистрировать конечную точку</p></td>
<td><p>Не удалось зарегистрировать конечную точку</p>
<p>Если проблема не устранена, обратитесь в службу поддержки продукта.</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Ошибка</p></td>
<td><p>IM MCU недоступен</p></td>
<td><p>IM MCU недоступен</p>
<p>Проверьте, запущен ли IM MCU</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя подключения к IM MCU</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Ошибка</p></td>
<td><p>AV MCU недоступен</p></td>
<td><p>AV MCU недоступен</p>
<p>Проверьте, запущен ли AV MCU</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя подключения к AV MCU</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Ошибка</p></td>
<td><p>AS MCU недоступен</p></td>
<td><p>AS MCU недоступен</p>
<p>Проверьте, запущен ли AS MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя подключения к AS MCU</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Ошибка</p></td>
<td><p>MCU данных недоступен</p></td>
<td><p>MCU данных недоступен</p>
<p>Проверьте, запущен ли MCU данных</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя подключения к MCU данных</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается присоединиться к IM MCU</p></td>
<td><p>Не удается присоединиться к IM MCU</p>
<p>Проверьте, запущен ли IM MCU</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается присоединиться к AV MCU</p></td>
<td><p>Не удается присоединиться к AV MCU</p>
<p>Проверьте, запущен ли AV MCU</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается присоединиться к AS MCU</p></td>
<td><p>Не удается присоединиться к AS MCU</p>
<p>Проверьте, запущен ли AS MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается присоединиться к MCU данных</p></td>
<td><p>Не удается присоединиться к MCU данных</p>
<p>Проверьте, запущен ли MCU данных</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Ошибка</p></td>
<td><p>Не удается получить доступ к Active Directory для фотографии</p></td>
<td><p>Недоступно подключение к Active Directory</p>
<p>Убедитесь в доступности соединения с Active Directory</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Информационный</p></td>
<td><p>Восстановление после сбоя доступа к Active Directory для фотографии</p></td>
<td><p>Н/Д</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Предупреждение</p></td>
<td><p>Не удается выполнить десериализацию</p></td>
<td><p>Не удается выполнить десериализацию</p>
<p>Если проблема не устранена, обратитесь в службу поддержки продукта.</p></td>
</tr>
</tbody>
</table>

