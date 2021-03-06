﻿---
title: 'Lync Server 2013: установка средства планирования'
TOCTitle: Установка средства планирования
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg615046(v=OCS.15)
ms:contentKeyID: 52058443
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка средства планирования в Lync Server 2013

 

_**Дата изменения раздела:** 2013-11-07_

Перед началом разработки и планирования инфраструктуры Lync Server 2013 с помощью планирования Microsoft Lync Server 2013 необходимо сначала установить планирования. планирования не требуется развертывать на рабочей станции или сервере, входящих в состав домена или инфраструктуры, где планируется устанавливать Lync Server 2013. Файл Readme, поставляемый вместе с планирования, содержит важные сведения об установке и использовании этого средства. Некоторые сведения из файла Readme продублированы здесь для большей ясности.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>планирования требует установки пользователем с правами и разрешениями администратора на компьютере, на котором средство будет устанавливаться.</td>
</tr>
</tbody>
</table>


Для установки и работы планирования поддерживаются следующие операционные системы:

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, 32-разрядный выпуск;

  - Windows 7, 64-разрядный выпуск с применением технологии Windows on Win32 (WOW);

  - Windows Server 2008 R2, с применением технологии WOW.

Кроме того, планирования требует Microsoft .NET Framework 4.5.

После того как выполнены условия начала установки, можно установить планирования.

## Установка средства планирования

1.  Войдите на локальный компьютер как член группы "Администраторы".

2.  С помощью проводника или окна командной строки найдите каталог, в который были загружены установочные файлы планирования.

3.  Найдите файл LyncPlanningTool.msi. В проводнике дважды щелкните файл. В окне командной строки введите имя файла и нажмите клавишу **ВВОД**, чтобы запустить файл.

4.  На странице приветствия **Microsoft Lync Server 2013, мастер установки средства планирования** нажмите кнопку **Далее**.

5.  Просмотрите **Лицензионное соглашение**, установите флажок **Я принимаю условия лицензионного соглашения**, если вы принимаете условия использования по лицензионному соглашению, и затем нажмите кнопку **Далее**.

6.  Выберите папку, в которую следует установить файлы средства планирования. Расположение по умолчанию – C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool. Если требуется изменить папку установки, нажмите кнопку **Изменить**. В окне **Изменение конечной папки** найдите или введите расположение для установки файлов, нажмите кнопку **ОК**, а затем кнопку **Далее**.

7.  Программа установки теперь готова к установке планирования. Нажмите кнопку **Установить**, чтобы начать процесс установки.

8.  Начнется установка, и будет отображаться ход процесса. После успешного завершения установки нажмите кнопку **Готово**.

9.  планирования готово к использованию.

## См. также

#### Концепции

[Установка дополнительного программного обеспечения в Lync Server 2013](lync-server-2013-installing-optional-software.md)

