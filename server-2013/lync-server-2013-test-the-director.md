﻿---
title: 'Lync Server 2013: проверка директора'
TOCTitle: Проверка директора
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398767(v=OCS.15)
ms:contentKeyID: 49310587
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Проверка директора в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-08_

На данном этапе у вас уже есть настроенный директор или пул директоров, но в соответствии с записями SRV системы доменных имен (DNS) клиенты должны входить в систему с использованием пула или сервера Standard Edition. Перед изменением записи DNS таким образом, чтобы клиенты Lync 2013 могли выполнять автоматический вход в систему с помощью директора, выполните тестирование клиента, вручную указав для него директора.

## Тестирование развертывания

1.  Выполните вход в систему компьютера, на котором установлена панель управления управления Lync Server, с использованием учетной записи домена, которая является частью группы **CSAdministrator** .

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации щелкните **Топология** и убедитесь, что в столбце **Состояние** имеется зеленый сервер со стрелкой (то есть ![Значок сервера с зеленой стрелкой](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Значок сервера с зеленой стрелкой")) для директора или пула директоров.

4.  Подключите два клиентских компьютера, на которых установлен клиент Lync Server 2013, и выполните вход с использованием другой учетной записи с поддержкой Lync Server 2013 на каждом компьютере.

5.  На одном из клиентских компьютеров щелкните меню **Параметры** , выберите группу параметров **Личные** , щелкните **Дополнительно** , щелкните **Настроить вручную** , а затем задайте для параметра **Имя или IP-адрес внутреннего сервера** полное доменное имя нового директора или пула директоров.

6.  Выполните вход в систему на обоих клиентских компьютерах и убедитесь, что клиент, которой выполняет вход с помощью директора, может успешно входить в систему, просмотрите состояние присутствия другого пользователя и убедитесь, что они могут обмениваться мгновенными сообщениями.

