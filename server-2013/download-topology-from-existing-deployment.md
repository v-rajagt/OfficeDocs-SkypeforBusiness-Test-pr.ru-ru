﻿---
title: загрузка топологии из существующего развертывания;
TOCTitle: загрузка топологии из существующего развертывания;
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49888228
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# загрузка топологии из существующего развертывания;

 

_**Дата изменения раздела:** 2012-09-29_

При создании пула Lync Server 2013 вы используете центральное хранилище управления, связанное с Lync Server 2010. При запуске построителя топологий при первом использовании и в последующих сеансах редактирования, отображается запрос на ввод расположения, из которого построитель топологий должен загрузить текущий документ конфигурации. Так как топология Lync Server 2010 уже определена и настроено центральное хранилище управления, следует выбрать вариант загрузки топологии из существующего развертывания. Построитель топологии прочитает базу данных и извлечет текущее определение.

**Загрузка топологии из существующего развертывания**

1.  Откройте **мастер развертывания Lync Server** .

2.  На странице **Lync Server 2013 – мастер развертывания** нажмите кнопку **Установить средства администрирования** .

3.  Запустите построитель топологий: нажмите **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** , затем выберите **Построитель топологий Lync Server**.

4.  Выберите параметр **Загрузить топологию из существующего развертывания**.
    
    ![Мастер развертывания, параметры построителя топологии](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Мастер развертывания, параметры построителя топологии")

5.  Выберите имя файла и сохраните топологию с типом файла по умолчанию (TBXML).

6.  Разверните узел Lync Server, как показано, чтобы отобразить различные роли сервера в развертывании.
    
    ![Построитель топологии, общие свойства ролей сервера](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Построитель топологии, общие свойства ролей сервера")

