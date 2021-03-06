﻿---
title: 'Lync Server 2013: технические требования к IPv6'
TOCTitle: Технические требования к IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205278(v=OCS.15)
ms:contentKeyID: 49311189
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Технические требования к IPv6 в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Если вы планируете настроить Lync Server 2013 для использования IPv6, помните о следующих требованиях.

  - Чтобы использовать IPv6-адреса с Lync Server, необходимо создать записи DNS для записей, которые нужно обнаружить и разрешить в IPv6-адрес. Служба DNS для IPv6 использует записи узла AAAA (quad-A). Если в развертывании используются IPv4 и IPv6, лучше всего настроить и поддерживать записи A узла для IPv4 и записи AAAA для IPv6. Даже если полностью переводите развертывание на IPv6, вам по-прежнему могут потребоваться записи DNS для IPv4 для внешних пользователей, которые все еще применяют IPv4.
    
    Можно развернуть записи узла DNS для IPv6 перед началом использования IPv6. Если клиент или сервер не используют IPv6, запись не будет указываться. Технологии туннелирования будут принимать решение относительно того, какую запись следует использовать, в зависимости от конфигурации технологии туннелирования и политик.

  - Каждый адрес IPv6 обладает определенной областью. Для IPv6-адресации можно использовать три области: глобальные адреса IPv6 (аналогичные общедоступным адресам IPv4), уникальные локальные адреса IPv6 (аналогичные диапазонам частных адресов IPv4) и локальные адреса IPv6 каналов (аналогичные автоматическим частным IP-адресам в Windows Server для IPv4). Всем серверам в пуле должны быть назначены адреса IPv6, относящиеся к одной и той же области.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Адресация IPv6 – это сложный вопрос, который требует тщательного планирования при участии сотрудников отдела сетевых технологий и поставщика Интернет-услуг, чтобы гарантировать правильную работу адресов, назначаемых на уровне Windows Server и уровне Lync Server 2013. Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</td>
</tr>
</tbody>
</table>


## См. также

#### Другие ресурсы

[Архитектура IP-адресации версии 6](http://tools.ietf.org/html/rfc4291)  
[Глобальный формат IPv6-адресов для одноадресной рассылки](http://tools.ietf.org/html/rfc3587)  
[Уникальные локальные IPv6-адреса для одноадресной рассылки](http://tools.ietf.org/html/rfc4193)

