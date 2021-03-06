﻿---
title: 'Lync Server 2013: параметры согласования для федеративных XMPP-партнеров'
TOCTitle: Параметры согласования для федеративных XMPP-партнеров
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49311598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Параметры согласования для федеративных XMPP-партнеров в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

В конфигурации XMPP-партнера доступно значительное количество возможных комбинаций параметров для типов согласования. Но не все эти комбинации являются допустимыми. В приведенной здесь таблице подробно описывается, какие параметры являются допустимыми, а какие – нет. Распространенные конфигурации представлены в первой таблице, во второй таблице приведены все возможные комбинации. Обратите внимание на то, что вы можете использовать *SASL* (Simple Authentication and Security Layer) **только** при включенном протоколе *TLS* (Transport Layer Security). Данные SASL отправляются в незашифрованном (пригодном для чтения) формате, поэтому при их передаче следует использовать другие средства защиты, такие как TLS.

### Распространенные методы согласования федерации XMPP

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Проверка подлинности с обратным вызовом</th>
<th>Ожидаемые методы проверки подлинности</th>
<th>Примечания.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обязательный?</p></td>
<td><p>Обязательный?</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><p>Обязательное использование TLS и SASL помогает обеспечить безопасность потока сообщений SASL. Обратный вызов недоступен и не может применяться в качестве резервного метода, если федеративный XMPP-партнер не установил обязательное или необязательное использование TLS.</p></td>
</tr>
<tr class="even">
<td><p>Обязательный?</p></td>
<td><p>Необязательный</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>Если федеративный XMPP-партнер установил обязательное или необязательное использование SASL, в случае обязательного использования TLS применяется SASL. Если SASL недоступен, используется обратный вызов через TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Необязательный</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>Хотя эти параметры и обеспечивают гибкость с точки зрения доступных методов согласования, они основаны на параметрах XMPP-партнера федерации. Если партнер задает обязательное или необязательное использование TLS, но SASL не поддерживается, будет доступен обратный вызов через TLS. Если партнер задает обязательное или необязательное использование TLS и SASL, используется оптимальный вариант TLS через SASL.</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Во многих случаях обратный вызов TCP является единственным возможным решением и обеспечивает некоторый уровень доверия, хотя желательно использовать другие варианты.</p></td>
</tr>
</tbody>
</table>


### Полная матрица методов согласования федерации XMPP

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Проверка подлинности с обратным вызовом</th>
<th>Ожидаемый метод проверки подлинности</th>
<th>Примечания, предупреждение или ошибка для недействительной конфигурации</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обязательный?</p></td>
<td><p>Обязательный?</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Обратный вызов не будет работать, если требуется как SASL, так и TLS.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Обязательный?</p></td>
<td><p>Обязательный?</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Обязательный?</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Обязательный?</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Обязательный?</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Обязательный?</p></td>
<td><p>False</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Недопустимая конфигурация</td>
</tr>
</tbody>
</table>

</div></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поскольку для SASL требуется TLS, который недоступен, комбинация SASL/TLS не работает. Для обратного вызова TCP устанавливается недопустимое состояние, и данный метод использовать нельзя.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Обязательный?</p></td>
<td><p>Необязательный</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS, обратный вызов TLS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Обязательный?</p></td>
<td><p>Необязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Необязательный</p></td>
<td><p>True</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Необязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Необязательный</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Необязательный</p></td>
<td><p>False</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Недопустимая конфигурация</td>
</tr>
</tbody>
</table>

</div></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Обязательный?</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Конфигурация допускает использование обратного вызова TLS.</p></td>
</tr>
<tr class="even">
<td><p>Обязательный?</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо включить SASL или обратный вызов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>В соответствии с вариантами согласования, включенными для другой конечной точки, будет принят обратный вызов TCP или TLS.</p></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо включить SASL или обратный вызов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Обратный вызов TCP является единственным доступным методом согласования</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412910.warning(OCS.15).gif" title="warning" alt="warning" />Предупреждение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Необходимо включить SASL или обратный вызов.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
</tbody>
</table>

