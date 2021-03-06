﻿---
title: Миграция с Lync Server 2010 на Lync Server 2013
TOCTitle: Миграция с Lync Server 2010 на Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205369(v=OCS.15)
ms:contentKeyID: 49311599
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Миграция с Lync Server 2010 на Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-17_

В подразделах данного раздела описывается процесс миграции с Lync Server 2010 на Lync Server 2013.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.</td>
</tr>
</tbody>
</table>


В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.

В этом документе используются термины, указанные в следующем списке.

  - *миграция*   
    Перемещение производственного развертывания с предыдущей версии Lync Server 2010 на Lync Server 2013.

<!-- end list -->

  - *обновление*   
    Установка более новой версии программного обеспечения на сервере или клиентском компьютере.

<!-- end list -->

  - *сосуществование*   
    Временная среда, существующая во время миграции, когда некоторые функциональные возможности уже перенесены в Lync Server 2013, а другие все еще остаются в предыдущей версии Lync Server 2010.

<!-- end list -->

  - *взаимодействие*   
    Способность вашего развертывания успешно работать во время периода сосуществования.

## Содержание

  - [Подготовка к миграции](before-you-begin-the-migration.md)

  - [Этап 1: планирование миграции от Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Этап 2: подготовка к миграции](phase-2-prepare-for-migration.md)

  - [Этап 3: развертывание пилотного пула Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Этап 5: добавление пограничного сервера Lync Server 2013 в пилотный пул](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Этап 6: переход от пилотного развертывания к рабочей версии](phase-6-move-from-pilot-deployment-into-production.md)

  - [Этап 7: выполнение послемиграционных задач](phase-7-complete-post-migration-tasks.md)

  - [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md)

