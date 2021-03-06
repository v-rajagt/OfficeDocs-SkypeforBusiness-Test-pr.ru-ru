﻿---
title: 'Lync Server 2013: делегирование'
TOCTitle: Делегирование
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994045(v=OCS.15)
ms:contentKeyID: 52058271
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Делегирование в Lync Server 2013

 

_**Дата изменения раздела:** 2013-03-09_

Ниже описано, как маршрутизация на основе местоположения влияет на функции делегирования в Lync.

  - Когда делегат, для которого включена маршрутизация на основе местоположения, совершает звонок от имени руководителя, звонок авторизуется на основе политики голосовой связи делегата, а для его маршрутизации используется политика маршрутизации голосовых звонков делегата.

  - Что касается исходящих звонков ТСОП в адрес руководителя, здесь действуют те же правила, регламентирующие переадресацию звонков и порядок обработки одновременных звонков, как описано в соответствующих разделах.

  - Когда делегат устанавливает конечную точку ТСОП в качестве точки назначения одновременных звонков для входящих звонков в адрес руководителя, для маршрутизации звонка на конечную точку ТСОП делегата используется политика маршрутизации голосовых звонков сетевого сайта, связанного с входящей магистралью.

  - Для целей делегирования, как правило, рекомендуется располагать руководителя и связанных с ним делегатов на одном сетевом сайте.

## См. также

#### Другие ресурсы

[Сценарии маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

