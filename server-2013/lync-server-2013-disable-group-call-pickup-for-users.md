﻿---
title: Отключение функции группового ответа на звонки для пользователей
TOCTitle: Отключение функции группового ответа на звонки для пользователей
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945638(v=OCS.15)
ms:contentKeyID: 52058285
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Отключение функции группового ответа на звонки для пользователей

 

_**Дата изменения раздела:** 2013-01-30_

Используйте следующую процедуру для отключения группового ответа на звонки для пользователя.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Когда вы отключаете функцию группового ответа на звонки для пользователя, номер группового ответа на звонки, который был назначен пользователю, не сохраняется. Если вы впоследствии повторно включаете функцию группового ответа на звонки для данного пользователя, необходимо снова назначить номер группового ответа на звонки с помощью параметра /enablegrouppickup.</td>
</tr>
</tbody>
</table>


## Отключение функции группового ответа на звонки для пользователя

1.  Войдите в качестве администратора на компьютер, на котором установлено средство SEFAUtil.

2.  В командной строке введите следующую команду:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Пример:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## См. также

#### Задачи

[Назначение пользователям номеров для группового ответа на звонки](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Включение группового ответа на звонки для пользователей](lync-server-2013-enable-group-call-pickup-for-users.md)

