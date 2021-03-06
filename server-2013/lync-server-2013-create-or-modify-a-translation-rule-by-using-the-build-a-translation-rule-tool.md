﻿---
title: Создание или изменение правила преобразования с помощью средства построения правила преобразования
TOCTitle: Создание или изменение правила преобразования с помощью средства построения правила преобразования
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412909(v=OCS.15)
ms:contentKeyID: 49310965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение правила преобразования с помощью средства построения правила преобразования

 

_**Дата изменения раздела:** 2012-10-05_

Выполните следующие действия, чтобы создать правило преобразования путем ввода ряда значений в средстве **Build a Translation Rule** (Создание правила преобразования) и разрешить панели управления Lync Server создание шаблона поиска соответствия и правила преобразования. В качестве альтернативного варианта можно задать шаблон поиска соответствия и правило преобразования вручную с помощью регулярного выражения. Дополнительные сведения см. в разделе [Создание или изменение правила преобразования вручную](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

## Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Прежде чем приступить к созданию правила преобразования, выполните действия, описанные в разделе [Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) (шаги с 1 по 10), или действия, описанные в разделе [Настройка магистрали без обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) (шаги с 1 по 9).

4.  На странице **New Translation Rule** (Создание правила преобразования) или **Edit Translation Rule** (Изменение правила преобразования) в поле **Name** (Имя) введите описательное имя правила преобразования.

5.  В поле **Description** (Описание) введите описание правила преобразования, например, **US International long-distance dialing** (Международные и междугородние звонки США) (необязательно).

6.  В разделе **Build a Translation Rule** (Создание правила преобразования) введите следующие значения:
    
      - **Starting digits** (Начальные цифры номера). Укажите первые цифры номеров для поиска соответствия (необязательно). Например, для поиска номеров в формате E.164, которые начинаются с символа +, введите **+**
    
      - **Length** (Длина). Укажите число цифр шаблона и укажите, должны ли цифры номера соответствовать всему шаблону, минимальному числу цифр шаблона или любому числу цифр шаблона. Например, введите **11** и в раскрывающемся списке выберите **At least** (Минимум) для поиска номеров, состоящих как минимум из 11 цифр.
    
      - **Digits to remove** (Число удаляемых цифр). Укажите число начальных цифр, которые необходимо удалить (необязательно). Например, чтобы отделить цифры номера от символа **+**, введите значение **1**.
    
      - **Digits to add** (Число добавляемых цифр). Укажите цифры, добавляемые в начало преобразуемых номеров (необязательно). Например, если вы хотите, чтобы при применении правила преобразования в начало номеров добавлялись цифры 011, введите значение **011**.
    
    Значения, вводимые в этих полях, отражаются в полях **Pattern to match** (Шаблон для поиска соответствия) и **Translation rule** (Правило преобразования). Например, если вы ввели значения, показанные в предыдущем примере, в поле **Pattern to match** (Шаблон для поиска соответствия) будет добавлено следующее регулярное выражение:
    
    **^\\+(\\d{9}\\d+)$**
    
    Поле **Translation rule** (Правило преобразования) задает шаблон для формата преобразованных номеров. Этот шаблон состоит из 2 частей:
    
      - Значение (например, **$1**), которое представляет число цифр в шаблоне соответствия
    
      - Значение, добавляемое перед номером, которое вводится в поле **Digits to add** (Число добавляемых цифр) (необязательно)
    
    Для значений предыдущего примера в поле **Translation rule** (Правило преобразования) будет отображаться **011$1**.
    
    После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.

7.  Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.

8.  Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.

9.  На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <strong>Commit all</strong> (Сохранить все), чтобы опубликовать изменение конфигурации. Дополнительные сведения см. в разделе <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</a> документации по операциям.</td>
    </tr>
    </tbody>
    </table>


## См. также

#### Задачи

[Создание или изменение правила преобразования вручную](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Настройка магистрали без обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Концепции

[Глобальные параметры обхода сервера-посредника в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

