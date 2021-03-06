﻿---
title: Требования к пропускной способности сети для трафика мультимедиа в Lync Server 2013
TOCTitle: Требования к пропускной способности сети для трафика мультимедиа в Lync Server 2013
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49888071
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Требования к пропускной способности сети для трафика мультимедиа в Lync Server 2013

 

_**Дата изменения раздела:** 2015-09-24_

Важной частью планирования сети является процесс, позволяющий гарантировать, что ваша сеть сможет обработать трафик мультимедиа, созданный Lync Server. Этот раздел поможет вам спланировать обработку такого трафика.

## Использование сети для трафика мультимедиа

Подсчет использования полосы пропускания для трафика мультимедиа может быть сложной задачей из-за числа различных переменных, таких как использование кодеков, разрешение и уровни активности. Использование полосы пропускания — это функция, зависящая от используемого кодека и активности потока, переменных, значения которых сильно отличаются в разных сценариях. В следующей таблице перечислены аудиокодеки, часто используемые в сценариях Lync Server 2013.

### Полоса пропускания аудиокодека

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Аудиокодек</th>
<th>Сценарии</th>
<th>Скорость полезной нагрузки аудио (кбит/с)</th>
<th>Полоса пропускания полезной нагрузки аудио и только IP-заголовков (кбит/с)</th>
<th>Полоса пропускания полезной нагрузки аудио, IP-заголовков, UDP, RTP и SRTP (кбит/с)</th>
<th>Полоса пропускания полезной нагрузки аудио, IP-заголовков, UDP, RTP, SRTP и ошибок, исправленных методом прямой коррекции (кбит/с)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Широкополосная служба RTAudio</p></td>
<td><p>Одноранговая</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>Узкополосная служба RTAudio</p></td>
<td><p>Одноранговая, ТСОП</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Конференции</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>G.722 Стерео</p></td>
<td><p>Одноранговая, конференции</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>ТСОП</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Кодек Siren</p></td>
<td><p>Конференции</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Показатели полосы пропускания в предыдущей таблице основаны на пакетизации 20 мс (50 пакетов в секунду), а для Siren и G.722 содержат дополнительные издержки протокола SRTP сценариев конференций. При этом предполагается, что поток активен на 100%. Метод прямой коррекции ошибок (FEC) используется динамически при потере пакетов в канал, чтобы сохранить качество аудиопотока.

Стереоверсия кодека G.722 используется системами на основе системы комнат Lync, которая позволяет применять стереомикрофоны, чтобы слушатели лучше различали выступающих на собрании.

Для видео кодеком по умолчанию является стандарт H.264/MPEG-4 Part 10 Advanced Video Coding, а также его масштабируемые расширения для временного масштабирования. Для обеспечения взаимодействия с клиентами Lync 2010 и Office Communicator 2007 R2 кодек RTVideo все так же используется для одноранговых звонков между Lync 2013 и устаревшими клиентами. В сеансах конференций и с теми, и с другими Lync 2013 и устаревшие клиенты Lync 2013 могут кодировать видео с помощью обоих видеокодеков и передавать битовый поток H.264 в Lync 2013, а поток RTVideo — клиентам Lync 2010 и Office Communicator 2007 R2.

Требуемая полоса пропускания зависит от разрешения, качества и частоты кадров. Для каждого разрешения существует две важных скорости передачи данных:

  - **Скорость передачи при максимальной полезной нагрузке**   Это скорость передачи данных, используемая конечной точкой Lync 2013 для разрешения с максимальной частотой кадров, поддерживаемым для этого разрешения. Это значение важно, так как оно обеспечивает наилучшее качество и максимальную частоту кадров для видео.

  - **Скорость передачи при минимальной полезной нагрузке**   Это скорость, ниже которая конечная точка Lync 2013 переключается на меньшее разрешение. Чтобы гарантировать определенное разрешение, доступная скорость передачи полезной нагрузки видео не должна быть меньше этой минимальной скорости для данного разрешения. Это значение важно, потому что вы можете понять минимальное допустимое значение, когда максимальная скорость передачи недоступна или не требуется. Для некоторых пользователей видео с такой низкой скоростью передачи может считать неприемлемым, поэтому будьте осторожны при рассмотрении таких скоростей. Обратите внимание, что для видеосцен без движения или с небольшими перемещениями пользователя фактическая скорость передачи данных может временно становиться меньше минимальной скорости.

Lync 2013 поддерживает многие другие разрешения. Это позволяет вам задавать разную полосу пропускания сети и возможности приема клиентов. Кроме того, отношение сторон по умолчанию для Lync 2013 изменилось на 16:9. Отношение 4:3 все еще поддерживается для веб-камер, которые не записывают видео с отношением сторон 16:9.

### Полоса пропускания разрешения видео

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Видеокодек</th>
<th>Разрешение и отношение сторон</th>
<th>Максимальная скорость полезной нагрузки видео (кбит/с)</th>
<th>Минимальная скорость полезной нагрузки видео (кбит/с)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Кодек H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>Кодек H.264/RTVideo</p></td>
<td><p>424x240 (16:9)</p>
<p>320x240 (4:3)</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>Кодек H.264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Кодек H.264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>Кодек H.264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>Кодек H.264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>Кодек H.264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>Кодек H.264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>Кодек H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>Кодек H.264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>Кодек H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


FEC для видео включается в скорость передачи полезной нагрузки видео, при использовании этого метода, поэтому нет отдельных значений с FEC для видео и без FEC для видео.

Конечные точки не передают потоковые пакеты аудио или видео непрерывно. В зависимости от сценария существуют различные уровни активности потока, указывающие, как часто пакеты передаются в потоке. Активность потока зависит от мультимедиа и сценария и не зависит от используемого кодека. В одноранговом сценарии:

  - Аудиопотоки отправляются из конечных точек, только когда пользователи говорят.

  - Оба участника получают аудиопотоки.

  - Если используется видео, обе конечные точки передают и получают видеопотоки в течение всего звонка.

  - Для видеосцен без движения или с небольшими перемещениями пользователя фактическая скорость передачи данных может временно становиться совсем небольшой, так как видеокодек пропускает области без изменения видео.

В сценарии конференций:

  - Аудиопотоки отправляются из конечных точек, только когда пользователи говорят.

  - Все участники получают аудиопотоки.

  - Если используется видео, все участники могут получать до пяти видеопотоков и один панорамный (например, с отношением сторон 20:3) видеопоток. По умолчанию пять видеопотоков основаны на журнале активного докладчика, но пользователи могут вручную выбрать участников, от которых они хотят получать видеопоток.

  - Каждый участник, который включает видеопоток пользователя, будет передавать один или несколько видеопотоков. Lync 2013 добавляет возможность передавать до пяти видеопотоков для оптимизации качества видео всех принимающих клиентов. Фактическое число передаваемых видеопотоков определяется отправителем на основе мощности ЦП, доступной полосы пропускания для передачи и числа принимающих клиентов, запросивших определенных видеопоток. Чаще всего передается один поток H.264 и один поток RTVideo, если устаревший клиент подключается к конференции. Другим распространенным сценарием является передача нескольких видеопотоков H.264 (например, с разным разрешением видео) для удовлетворения запросов различных принимающих клиентов.

Помимо полосы пропускания, необходимой для трафика RTP для аудио и видео, полоса пропускания требуется и для протокола RTCP. RTCP используется для статистики и управления потоком RTP. Для планирования используйте показатели из следующей таблицы для трафика RTCP. Эти значения представляют максимальную полосу пропускания, используемую для RTCP, и отличаются для аудио- и видеопотоков из-за различий в управляющих данных

### Полоса пропускания RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Мультимедиа</th>
<th>Максимальная полоса пропускания RTCP (кбит/с)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аудио</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Видео (только прием/передача H.264 или RTVideo)</p></td>
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>Видео (прием/передача H.264 или RTVideo)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Следующие две полосы пропускания представляют интерес для планирования мощности:

  - **Максимальная полоса пропускания без FEC**   Максимальная полоса пропускания, используемая потоком, включая типичные операции потока и типичный кодек, используемый в сценарии без FEC. Это полоса пропускания при 100% активности потока без потери пакетов, приводящей к использованию FEC.  Это значение применяется для вычисления полосы пропускания, которую нужно выделить, чтобы использовать кодек в данном сценарии. 

  - **Максимальная полоса пропускания с FEC**   Максимальная полоса пропускания, используемая потоком, включая типичные операции потока и типичный кодек, используемый в сценарии с FEC. Это полоса пропускания при 100% активности потока с потерей пакетов, приводящей к использованию FEC для улучшения качества.  Это значение применяется для вычисления полосы пропускания, которую нужно выделить, чтобы использовать кодек в данном сценарии и применить FEC для сохранения качества при потере пакетов. 

В следующей таблице также указано дополнительное значение полосы пропускания, **Типовая полоса пропускания**. Это средняя полоса пропускания, используемая потоком, включая типичные операции потока и типичный кодек, используемый в сценарии.  Ее можно использовать для приблизительной оценки доли полосы пропускания, используемой трафиком мультимедиа в заданный момент времени. Но это значение не следует использовать для планирования мощности, так как отдельные звонки будут превышать это значение при уровне активности выше среднего. Типовая полоса пропускания видеопотока в таблицах ниже основана на различных разрешениях, которые использовались в измеряемых данных пользователей. Например, в одноранговых сеансах большинство пользователей применяют окно отображения видео по умолчанию, а определенная часть пользователей увеличивает или разворачивает приложение Lync, чтобы получить более высокое разрешение видео.

В следующих таблицах представлены три значения полосы пропускания для различных сценариев.

### Планирование мощности аудио и видео для одноранговых сеансов

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Мультимедиа</th>
<th>Кодек</th>
<th>Типовая полоса пропускания потока (кбит/с)</th>
<th>Максимальная полоса пропускания потока без прямой коррекции ошибок (FEC)</th>
<th>Максимальная полоса пропускания потока с прямой коррекцией ошибок (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аудио</p></td>
<td><p>Широкополосная служба RTAudio</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Аудио</p></td>
<td><p>Узкополосная служба RTAudio</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Основное видео при вызове конечных точек Lync 2013</p></td>
<td><p>Кодек H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (для максимального разрешения 1920x1080)</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="even">
<td><p>Основное видео при вызове конечных точек Lync 2010 и Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (для максимального разрешения 1280x720)</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="odd">
<td><p>Панорамное видео при вызове конечных точек Lync 2013</p></td>
<td><p>Кодек H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (для максимального разрешения 1920x288)</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="even">
<td><p>Панорамное видео при вызове конечных точек Lync 2010 и Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (для максимального разрешения 960x144)</p></td>
<td><p>Не применимо</p></td>
</tr>
</tbody>
</table>


### Планирование мощности аудио и видео для конференций

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Мультимедиа</th>
<th>Типовой кодек</th>
<th>Типовая полоса пропускания потока (кбит/с)</th>
<th>Максимальная полоса пропускания потока без прямой коррекции ошибок (FEC)</th>
<th>Максимальная полоса пропускания потока с прямой коррекцией ошибок (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аудио</p></td>
<td><p>G.722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Аудио</p></td>
<td><p>Кодек Siren</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Прием основного видео</p></td>
<td><p>H.264 и/или RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="even">
<td><p>Передача основного видео</p></td>
<td><p>H.264 и/или RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="odd">
<td><p>Прием панорамного видео</p></td>
<td><p>H.264 и/или RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (для максимального разрешения 1920x288)</p></td>
<td><p>Не применимо</p></td>
</tr>
<tr class="even">
<td><p>Передача панорамного видео</p></td>
<td><p>H.264 и/или RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (для передачи битовых потоков с несколькими разрешениями или кодеками)</p></td>
<td><p>Не применимо</p></td>
</tr>
</tbody>
</table>


Для основного видео типовая и максимальная полоса пропускания потока — это объединенная полоса пропускания для всех принимаемых видеопотоков и всех передаваемых видеопотоков соответственно. Даже с несколькими видеопотоками типовая полоса пропускания меньше, чем в одноранговом сценарии, так как множество видеоконференций используют общий доступ к контенту, что приводит к намного меньшим окнам видео и, соответственно, меньшим разрешениям видео. Максимальная поддерживаемая объединенная полоса пропускания видео — 8000 кбит/с для приема и передачи потоков, что можно использовать, например, при наличии двух входящих видеопотоков с разрешением 1920x1080p.

Типовая полоса пропускания потока для панорамного видео основана на текущих доступных устройствах, которые могут передавать в потоке только панорамное видео разрешением до 960x144. После выпуска устройств с разрешением панорамного видео 1920x288 ожидается, что типовая полоса пропускания потока увеличится.

### Планирование мощности аудио для ТСОП

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Мультимедиа</th>
<th>Типовой кодек</th>
<th>Типовая полоса пропускания потока (кбит/с)</th>
<th>Максимальная полоса пропускания потока без прямой коррекции ошибок (FEC)</th>
<th>Максимальная полоса пропускания потока с прямой коррекцией ошибок (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аудио</p></td>
<td><p>G.711</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Аудио</p></td>
<td><p>Узкополосная служба RTAudio</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


Показатели полосы пропускания сети в этих таблицах представляют только односторонний трафик и включают 5 кбит/с издержек трафика RTCP для каждого потока. Для вычисления максимального видеопотока используется максимальная скорость передачи видео.

