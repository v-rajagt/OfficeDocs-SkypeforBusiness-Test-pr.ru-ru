﻿---
title: 'Lync Server 2013: мониторинг производительности сети'
TOCTitle: Мониторинг производительности сети
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn720923(v=OCS.15)
ms:contentKeyID: 62246675
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Мониторинг производительности сети в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Lync Server 2013 — это технология взаимодействия в режиме реального времени, которая полностью зависит от сети в рамках обеспечения взаимодействия между пользователями посредством обмена мгновенными сообщениями, голосовыми вызовами или видеосвязи. Поэтому важно отслеживать производительность сети постоянно, чтобы гарантировать наилучший опыт работы выбранной пользователем модальности взаимодействия.

Производительность сети можно измерить на двух уровнях:

  - **Общая производительность сети** Этот уровень измерения производительности позволяет организации создать общий вид сети и обычно реализовывается посредством сторонних систем мониторинга сети. Данные системы получают данные о производительности и емкости от удаленных сетевых устройств, таких как маршрутизаторы и коммутаторы все сети в целом, что позволяет администраторам определить работоспособность любого указанного сетевого компонента в любое время.

  - **Производительность отдельного сервера** Этот уровень измерения производительности ограничен определенным сервером и помогает администраторам с оценкой производительности сети определенного сервера для устранения характерных проблем производительности или оценки производительности соответствующего сервера в рамках указанного периода времени в качестве части процесса планирования емкости.

Мониторинг сети можно выполнять с помощью инструментов, описанных в следующих разделах.

## Инструменты для мониторинга общей производительности сети

## System Center Operations Manager 2012

System Center Operations Manager предоставляет сквозное управление службами, удобное для настройки и расширения, что позволяет повысить уровни обслуживания для всей ИТ-среды. Это позволяет командам операций и управления ИТ-средой определять и устранять проблемы, влияющие на работоспособность распределенных ИТ-служб. Сквозное управление службами не ограничивается средами на основе компонентов Microsoft. Поддержка для веб-служб для управления (WS-Management), протокола SNMP и партнерских решений позволяет системам, которые не работают на основе ОС и оборудования Microsoft, быть включенными в мониторинг служб в рамках System Center Operations Manager 2012.

## System Center Operations Manager 2012 и сторонние решения по управлению сетями

**EMC Smarts** Решения EMC для диспетчеров операций позволяет быстро устранять проблемы, влияющие на повсеместные уровни обслуживания. Использование решений EMC для диспетчеров операций позволяет управлять и отслеживать всю цепочку ИТ-служб полностью с помощью одного интегрированного и автоматизированного решения. Основные проблемы производительности и доступности будут определены с легкостью, а устранение будет выполнено быстрее, что позволит сократить уровень влияния и затраты. Основные преимущества указаны далее.

  - Простое в использовании управление с расширенными возможностями. Ориентируется на предоставление стратегического бизнес-значения вместо ручной сортировки и фильтрации беспорядочных оповещений.

  - **Быстрое разрешение**. Более быстрое решение ИТ-проблем и отклик на бизнес-требования с сокращением затрат времени и денег. т.

  - **Упрощение операций**. Избегание сложной ИТ-среды с помощью объединения нескольких инструментов управления, приложений и терминалов.

Дополнительную информацию можно найти в следующих разделах:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Решения для Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

## Решения сторонних производителей

**HP Network Management Center (ранее известное как HP OpenView)**. [HP Network Management Center](https://h10078.www1.hp.com/cda/hpms/display/main/hpms_content.jsp?zn=bto%26cp=1-11-15-119_4000_100) предоставляет встроенное управление отказоустойчивостью и производительностью для улучшения уровня доступности и производительности сети. Решение Network Management Center является частью решения по автоматизированному управлению сетями от HP, которое объединяет управление отказоустойчивостью, производительностью, конфигурацией и изменениями.

**Продукты Cisco Network Management and Automation**. Для предприятий Cisco предоставляет несколько продуктов управления, включая решение CiscoWorks LAN Management Solution и модуль Cisco Network Analysis Module, в рамках помощи улучшения эксплуатационной эффективности и для сокращения времени простоя сети. Дополнительные сведения по этим продуктам см. на веб-сайте Cisco по адресу: [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

Протокол SNMP. Протокол SNMP является стандартом управления сетью, который определяет стратегию для управления сетями TCP/IP. SNMP позволяет захватывать информацию о конфигурации и состоянии сети, а также отправлять ее на выделенный компьютер для мониторинга события. Данный протокол управления сетью на основе стандартов использует распределенную архитектуру, которая содержит следующие компоненты:

  - Множественные управляемые узлы, каждый с объектом SNMP называемым "агент", который предоставляет удаленный доступ к инструментарию управления.

  - Не менее одного объекта SNMP, известного как "диспетчер", который запускает приложения управления для мониторинга и контроля управляемыми элементами. Управляемыми элементами являются устройства, такие как хосты, маршрутизаторы и т. д. Они отслеживаются и управляются с помощью доступа к их информации управления.

  - Протокол управления SNMP используется для передачи информации управления между станциями и агентами управления. Информация об управлении относится к управляемым объектам, которые находятся в виртуальном хранилище информации под названием база информации для управления (база MIB).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Примеры сторонних решений по мониторингу сети представлены выше. Этот список не является окончательным и Microsoft не отдает предпочтение решению какого-либо определенного поставщика. Обратитесь к поставщику сетевых служб или соответствующему поставщику технологий для определения наилучшего решения по мониторингу сети для вашей организации.</td>
</tr>
</tbody>
</table>


## Инструменты для мониторинга производительности сети отдельного сервера

## System Center Operations Manager 2012

System Center Operations Manager 2012 позволяет администраторам просматривать производительность сети отдельных серверов посредством пакета управления Windows Server 2012. Пакет управления ОС Windows Server содержит пакет управления производительностью, который позволяет администраторам выполнять мониторинг производительности сетевого адаптера и его работоспособность.

## Сетевой монитор Windows

Сбор, отображение и анализ использования ресурсов на сервере, а также измерение сетевого трафика. Сетевой монитор отслеживает исключительно активность сети. С помощью захвата и анализа сетевых данных и использования их вместе с журналами производительности можно определить использование сети, выявить сетевые неполадки и спрогнозировать будущие потребности сети.

Дополнительные сведения о Network Monitor 3.4, установке и настройке сетевого монитора, а также захвате и анализе данных см. в сеансе "Обзор Network Monitor 3.3". Сведения о сетевом мониторе также можно найти в блоге по адресу: <http://blogs.technet.com/b/netmon/>.

