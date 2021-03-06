﻿---
title: 'Lync Server 2013: настройка абонентских групп для конференц-связи с телефонным подключением'
TOCTitle: Настройка абонентских групп для конференц-связи с телефонным подключением
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412768(v=OCS.15)
ms:contentKeyID: 49310741
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-25_

При развертывании конференц-связи с телефонным подключением требуется создать или изменить одну абонентскую группу или несколько таких групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением. Убедитесь, что хотя бы одно правило нормализации в каждой абонентской группе преобразует добавочные номера в полные номера телефонов в формате E.164. Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона. Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, поэтому пользователи могут проходить проверку подлинности только с помощью добавочного номера.

Чтобы настроить абонентские группы для конференц-связи с телефонным подключением, выполните следующие действия:

  - Независимо от того, развертываете ли вы корпоративной голосовой связи, добавьте в глобальную абонентскую группу регион конференц-связи с телефонным подключением и убедитесь, что правило нормализации правильно преобразует номера доступа к конференц-связи с телефонным подключением. Дополнительные сведения см. в разделе [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Если развертывание корпоративной голосовой связи не планируется, то создайте абонентские группы для номеров доступа к конференц-связи с телефонным подключением. Не забудьте добавить регион конференц-связи с телефонным подключением. Подробные инструкции см. в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Если вы развернули корпоративной голосовой связи, добавьте в абонентские группы корпоративной голосовой связи регионы и используйте соответствующие правила нормализации для номеров доступа к конференц-связи с телефонным подключением. Подробные инструкции см. в разделе [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением. Подробные инструкции см. в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Дополнительные сведения о планировании регионов см. в разделе [Требования к связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) документации по планированию.

## Содержание

  - [Просмотр сведений об абонентских группах в Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Определение правил нормализации в Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

