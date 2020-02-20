---
title: 'Lync Server 2013: 백 엔드 Lync Server 저장소 성능 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>모니터링 백 엔드 Lync Server 2013 저장소 성능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-02_

Lync Server 2013 백 엔드 데이터베이스는 Lync Server 2013 배포에서 매우 중요 한 부분입니다. Lync Server 2013 백 엔드를 최적으로 수행 하 고 있는지 확인 하는 데 도움이 되도록 데이터베이스 및 각 트랜잭션 로그를 지속적으로 모니터링 하는 것이 좋습니다.

다음 표에는 저장소 성능에 대 한 정보를 파악 하기 위해 모니터링 해야 하는 성능 카운터가 나와 있습니다. 시스템이 스트레스를 받을 때 성능 변경을 이해 하기 위해 이러한 카운터의 초기 계획 값을 먼저 결정 해야 합니다 (시스템이 정상, 예상 되는 부하).

### <a name="performance-counters-to-be-monitored"></a>모니터링할 성능 카운터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>성능 카운터</th>
<th>기준 임계값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>초당 트랜잭션 (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>초당 트랜잭션 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>초당 트랜잭션 (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>로그 플러시/초 (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>로그 플러시/초 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>로그 플러시/초 (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>초당 디스크 전송-RTC db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>초당 디스크 전송-RTC 로그</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>초당 디스크 전송 rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>초당 디스크 전송 rtcdyn 로그</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

