﻿---
title: 'Lync Server 2013: входящие звонки'
TOCTitle: Входящие звонки
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994038(v=OCS.15)
ms:contentKeyID: 52058237
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Входящие звонки в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Маршрутизация входящих звонков для пользователей, которым разрешена маршрутизация на основе расположения, зависит от расположения конечной точки пользователя. Маршрутизация входящих звонков происходит описанным далее образом. Если пользователь принимает входящий вызов к конечной точке, расположенной на сетевом сайте с разрешенной маршрутизацией на основе расположения, а конечная точка находится на том же сетевом сайте, что и шлюз ТСОП, звонок будет переадресован. Если пользователь принимает входящий вызов к конечной точке, расположенной на сетевом сайте с разрешенной маршрутизацией на основе расположения, а конечная точка находится на сетевом сайте без шлюза ТСОП, звонок не будет переадресован. Если пользователь не имеет конечных точек, расположенных на том же сетевом сайте, что и шлюз ТСОП, с которого происходит входящий звонок, этот звонок будет переадресован на голосовую почту пользователя и уведомление о пропущенном звонке будет отправлено вызываемому абоненту.

Параметры переадресации звонков пользователей с включенной маршрутизацией на основе расположения будут по-прежнему применяться, но переадресация звонков будет ограничиваться маршрутизацией на основе расположения.

В приведенной ниже таблице показано, как маршрутизация на основе расположения влияет на маршрутизацию входящих звонков в зависимости от расположения конечной точки вызываемого абонента. Сетевой сайт шлюза ТСОП включен для маршрутизации на основе расположения, а она разрешает только маршрутизацию звонков ТСОП в конечных точках в пределах одного сайта сети.

### Вызываемый абонент получает входящий звонок от ТСОП

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Конечная точка вызываемого абонента расположена на том же сетевом сайте, что и шлюз ТСОП</th>
<th>Конечная точка вызываемого абонента не расположена на том же сетевом сайте, что и шлюз ТСОП</th>
<th>Конечная точка вызываемого абонента расположена на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Маршрутизация входящих звонков ТСОП</p></td>
<td><p>Входящий звонок направляется в конечные точки вызываемого абонента</p></td>
<td><p>Входящий звонок не направляется в конечные точки вызываемого абонента</p></td>
<td><p>Входящий звонок не направляется в конечные точки вызываемого абонента</p></td>
</tr>
</tbody>
</table>

  

## См. также

#### Другие ресурсы

[Сценарии маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

