﻿---
title: 'Lync Server 2013: установка пароля учетной записи Kerberos для проверки подлинности на сервере'
TOCTitle: Установка пароля учетной записи Kerberos для проверки подлинности на сервере
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398734(v=OCS.15)
ms:contentKeyID: 49310520
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка пароля учетной записи Kerberos для проверки подлинности на сервере в Lync Server 2013

 

_**Дата изменения раздела:** 2012-01-16_

Чтобы успешно выполнить данную процедуру, необходимо войти в систему с учетной записью пользователя, являющегося членом группы RTCUniversalServerAdmins.

Необходимо настроить пароль для учетной записи Kerberos для каждого узла с интерфейсными серверами, серверами Standard Edition и Директорами. Вы можете настроить пароль, выполнив командлет **Set-CsKerberosAccountPassword**  Windows PowerShell на одном сервере узла (например, переднего плана). Необходимо запустить командлет **Set-CsKerberosAccountPassword** для каждого узла. Этот командлет настраивает Службы IIS для службы служб и затем задает пароль для учетной записи компьютера в Доменные службы Active Directory. Альтернативный метод, основанный на том, какой параметр используется с командлетом, настраивает службы IIS на одном сервере, при этом использует другой сервер, настроенный как источник пароля учетной записи Kerberos.

При использовании командлета **Set-CsKerberosAccountPassword** для установки пароля, Kerberos задает в качестве пароля случайно созданную строку. Этот командлет обращается ко всем экземплярам IIS во всех центральных узлах Lync Server 2013, которым назначена эта учетная запись.

## Установка пароля учетной записи для проверки подлинности Kerberos

1.  Войдите на любой компьютер домена с установленным средством Командная консоль Lync Server как участник группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните следующие две команды:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Например:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Необходимо указать параметр UserAccount в формате &quot;Домен\пользователь&quot;. Формат &quot;Пользователь@домен.расширение&quot; не поддерживается для указания объектов компьютера, созданных для проверки подлинности Kerberos.</td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>После внесения любых изменений в систему проверку подлинности Kerberos (например, после добавления или удаления учетной записи) необходимо выполнить <strong>Enable-CsTopology</strong> в командной строке Командная консоль Lync Server.</td>
    </tr>
    </tbody>
    </table>

