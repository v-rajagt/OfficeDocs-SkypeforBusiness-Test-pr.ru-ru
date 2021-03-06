﻿---
title: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа'
TOCTitle: Разрешения и необходимые условия для настройки группы ответа
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204840(v=OCS.15)
ms:contentKeyID: 49309586
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Группа ответа – это функция управления вызовами корпоративной голосовой связи. В данном разделе описаны то, что нужно для настройки данной группы ответа, а также административные учетные данные и разрешения, необходимые для выполнения настройки.

Подразумевается, что вы ознакомились с документацией по планированию группы ответа. Дополнительные сведения см. в разделе [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) документации по планированию.

## Инструменты настройки и административные роли

Для настройки группы ответа можно использовать следующие административные средства:

  - управления Lync Server

  - настройки группы ответа

  - Командная консоль Lync Server

Для того чтобы настроить группы ответа, необходимо быть членом по крайней мере одной из следующих административных ролей:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Группа безопасности Active Directory (1)</strong></p></td>
<td><p>Создайте рабочий процесс</p></td>
<td><p>Назначьте менеджера</p></td>
<td><p>Создайте, назначьте агентов, очереди</p></td>
<td><p>Создайте дни праздников и рабочие часы</p></td>
<td><p>Активируйте или деактивируйте рабочий процесс</p></td>
<td><p>Настройте рабочий процесс (Интерактивное речевое взаимодействие (IVR) или сервисную группу)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>v(2)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>(1)</strong> Объект пользователя Доменные службы Active Directory должен быть членом указанной группы безопасности Active Directory. Администратор или другой делегированный член группы Active Directory с соответствующими правами на добавление пользователей к группе безопасности (например, Administrator, Account Operator) должен добавить объект пользователя к заявленной группе безопасности, чтобы пользователь мог выполнять перечисленные функции. <strong>(2)</strong> Только для рабочих процессов, которые CsResponseGroupAdministrator назначил CsResponseGroupManager. <strong>(3)</strong> Менеджер группы ответа может назначить другого члена CsResponseGroupManager рабочему процессу, которым текущий менеджер уже управляет. <strong>(4)</strong> Только CsViewOnlyAdministrator может запускать командлеты &quot; Get&quot; Командная консоль Lync Server.</td>
</tr>
</tbody>
</table>


## Необходимые требования для настройки группы ответа

Для группы ответа требуются следующие компоненты:

  - приложения

  - "Группа ответа"

  - Языковые пакеты

  - Хранилище файлов (для хранения аудиофайлов)

  - Веб-службы (включая настройки группы ответа и консоль выполнения входа и выхода агентов)

Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.

Перед настройкой групп ответа возможно потребуется сделать следующее:

  - Включить пользователей для Lync Server 2013 и корпоративной голосовой связи.

  - Изменить файл конфигурации для соответствия стандартам Federal Information Processing (FIPS).

  - Изменить параметры сортировки базы данных для поддержки символов транскрипций ий, мэн, цзан для названий очередей и групп агентов.

## Включение пользователей

Первым шагом при настройке группы ответа является создание групп агентов. Перед созданием группы агентов, нужно включить пользователей, которые будут агентами для групп ответаLync Server 2013 и корпоративной голосовой связи. Включение пользователей для Lync Server 2013 обычно выполняется при развертке сервера Enterprise Edition или Standard Edition. Дополнительные сведения о включении пользователей для Lync Server 2013 см. в разделе [Отключение и повторное включение учетных записей пользователей для Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Включение пользователей корпоративной голосовой связи обычно выполняется при развертке корпоративной голосовой связи. Дополнительные сведения по данному вопросу см. в [Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

## Соответствие требованиям стандарта FIPS

Данный подраздел касается вас, только если вашей организации необходимо соответствовать федеральному стандарту по (FIPS, США).

Чтобы соответствовать стандарту, после установки Web Services необходимо изменить файл Web.config уровня приложения на использование другого криптографического алгоритма. Нужно указать, чтобы ASP.NET использовал алгоритм Triple Data Encryption Standard (3DES) для обработки данных о состоянии просмотра. В случае "Группа ответа" данное требование касается настройки группы ответа и консоли регистрации и отмены регистрации агентов. Подробные сведения о данном требования в приведены в статье базы знаний Майкрософт 911722, «Возможно получение сообщения об ошибке при открытии веб-страниц ASP.NET, для которых включен параметр ViewState после обновления с ASP.NET 1.1 до ASP.NET 2.0» по адресу [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).

Чтобы изменить файл Web.config, сделайте следующее:

1.  В текстовом редакторе, например в Блокноте, файл Web.config уровня приложения.

2.  Найдите в нем подраздел `<system.web>`.

3.  Добавьте следующий блок `<machineKey>` в подраздел `<system.web>`:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Сохраните файл Web.config.

5.  Перезапустите службы Службы IIS выполнив следующую команду в командной строке:
    
        iisreset

## Поддержка символов транскрипций ий, мэн и цзан

Данный раздел относится к вам, только если вашей организации нужна поддержка подобных символов

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Дополнительные сведения о том, что такое символы ий, мэн и цзан и почему они могут быть важны для вашей развертки служб, см. в описании наборов символов GB18030 по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</a>.</td>
</tr>
</tbody>
</table>


Для поддержки данных символов необходимо изменить параметры сортировки базы данных Rgsconfig. Измените параметры сортировки столбца **Название** в следующих таблицах каждой базы данных Rgsconfig:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Для SQL Server 2008 R2 и SQL Server 2012 используйте параметры сортировки Latin\_General\_100 (Accent Sensitive). При использовании этих параметров сортировки все имена объектов не учитывают регистр.

Изменить параметры сортировки можно с помощью Microsoft SQL Server Management Studio. Подробные сведения об использовании данного инструменты приведены в статье «Использование SQL Server Management Studio» по адресу [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184). Чтобы изменить параметры сортировки, выполните следующее:

1.  Убедитесь в том, что SQL Server Management Studio настроен так, что можно было бы вносить изменения, требующие пересоздания таблиц. Смотрите статью "Диалоговое окно «Сохранение (не разрешено)» по адресу [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186). Подробные сведения о задании параметров сортировки столбца см. статью "Учебник, Как задать параметры сортировки столбцов (Visual Database Tools)" по адресу [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).

2.  Используя Microsoft SQL Server Management Studio подключитесь к базе данных Rgsconfig.

3.  Найдите нужную таблицу в базе данных Rgsconfig, щелкните ее правой кнопкой мыши и выберите **Конструктор** .

4.  Измените параметры сортировки столбца **Название** и сохраните таблицу.

