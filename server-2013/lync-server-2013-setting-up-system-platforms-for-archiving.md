﻿---
title: Настройка системных платформ для архивирования
TOCTitle: Настройка системных платформ для архивирования
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204768(v=OCS.15)
ms:contentKeyID: 49309305
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка системных платформ для архивирования

 

_**Дата изменения раздела:** 2012-10-09_

Прежде чем начинать развертывание компонента архивации, вам следует установить требуемую операционную систему и все остальное требуемое программное обеспечение на оборудовании, соответствующем требованиям к системе:

  - **Платформа системы Lync Server 2013**. Развертывания системы Lync Server 2013 не имеют серверов архивации. Вместо этого на серверах переднего плана и серверах Standard Edition запускаются унифицированные агенты по сбору данных для архивации, поэтому для размещения архивации отдельная системная платформа не требуется.

  - **Платформа хранения данных**. В системе Lync Server 2013 вы можете сохранять данные, используя один из следующих компонентов:
    
      - **Интеграция с Microsoft Exchange**. Если вы хотите сохранить архивные данные системы Lync Server 2013 с помощью развертывания Exchange 2013, то вместо настройки отдельной базы данных для хранения архивных данных или в дополнение к ней в развертывании Exchange должен выполняться Exchange 2013. Дополнительные сведения о настройке системных платформ для Exchange 2013 см. в документации по продукту Exchange.
    
      - **SQL Server**. Если для хранения архивных данных вы хотите использовать отдельную базу данных SQL Server, перед развертыванием архивации вам следует настроить системную платформу для базы данных вместо или в дополнение к интеграции с Microsoft Exchange. Конкретные требования к системной платформе зависят от того, используется ли Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 для базы данных архивации. Дополнительные сведения о настройке системных платформ для этих баз данных см. в документации по продуктам Microsoft SQL Server 2008 R2 и Microsoft SQL Server 2012.

  - **Платформа файлового сервера**. Система Lync Server 2013 сохраняет архивные файлы Lync Server том же расположении, которое вы указали для хранения файлов при настройке серверов переднего плана или серверов Standard Edition. Вы не можете указать отдельное расположение для хранения архивных файлов, поэтому соответствующая отдельная системная платформа не требуется. Если вы используете интеграцию с Microsoft Exchange, файлы Exchange 2013 для архивных коммуникаций Lync сохраняются на серверах Exchange 2013 для пользователей, расположенных на этих серверах Exchange.

