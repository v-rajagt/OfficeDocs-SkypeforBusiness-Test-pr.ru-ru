﻿---
title: Включение группового ответа на звонки для пользователей и назначение группового номера
TOCTitle: Включение группового ответа на звонки для пользователей и назначение группового номера
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945650(v=OCS.15)
ms:contentKeyID: 52058331
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение группового ответа на звонки для пользователей и назначение группового номера

 

_**Дата изменения раздела:** 2013-01-30_

После добавления номеров группового ответа в таблицу орбиты парковки вызовов необходимо назначить номера групп пользователям и включить для них групповой ответ на звонки. Для назначения номеров и включения группового ответа на звонки используйте средство набора ресурсов Secondary Extension Feature Activation (SEFAUtil).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, которые размещаются локально. Такие пользователи не могут участвовать в групповом ответе на звонки. То есть другие пользователи не могут отвечать на их вызовы, и они не могут отвечать на вызовы других пользователей.</td>
</tr>
</tbody>
</table>


## Назначение группового номера и включение группового ответа на звонки для пользователя

1.  Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2.  В командной строке выполните команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Например, чтобы назначить пользователю групповой номер 199, введите:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## См. также

#### Задачи

[Отключение функции группового ответа на звонки для пользователей](lync-server-2013-disable-group-call-pickup-for-users.md)

