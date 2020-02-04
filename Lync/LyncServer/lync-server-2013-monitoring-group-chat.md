---
title: 'Lync Server 2013: 그룹 채팅 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Lync Server 2013에서 그룹 채팅 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-08-04_

성능 향상을 위해 Microsoft 다운로드 센터에서 제공 하는 최신 [누적 서버 업데이트 설치 관리자](http://support.microsoft.com/kb/968802) 를 실행 하는 것이 좋습니다.

최신 누적 업데이트를 실행 하는 경우 메트릭 용 다음 스트레스 테스트 표를 사용 하 여 그룹 채팅 서버가 최적의 상태에서 실행 중인지 파악 합니다.

### <a name="test-environment-and-user-model"></a>테스트 환경 및 사용자 모델

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>그룹 채팅 풀에 있는 세 개의 그룹 채팅 서버 (각각 8gb 메모리 및 8 개 프로세서).</p></td>
</tr>
<tr class="even">
<td><p>두 개의 Lync Server 2013 프런트 엔드가 Enterprise Edition에서 끝납니다.</p></td>
</tr>
<tr class="odd">
<td><p>3 개의 그룹 채팅 서버에서 동시 사용자 6만.</p></td>
</tr>
<tr class="even">
<td><p>그룹 채팅 풀이 호스트 하는 25000 채널.</p></td>
</tr>
<tr class="odd">
<td><p>채널 크기:</p>
<ul>
<li><p>작은 채널 크기: 30</p></li>
<li><p>중간 채널 크기: 150</p></li>
<li><p>큰 채널 크기: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>채널 수:</p>
<ul>
<li><p>숫자 작은 채널: 24000</p></li>
<li><p>숫자 중간 채널 800</p></li>
<li><p>숫자 대형 채널 24</p></li>
<li><p>총 채널 24824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>채널 초대:</p>
<ul>
<li><p>채널의 절반은 초대 채널입니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>사용자가 참가 하는 채널 수:</p>
<ul>
<li><p>작음: 12</p></li>
<li><p>보통: 2</p></li>
<li><p>큼: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>참가 속도:</p>
<ul>
<li><p>총 10 개/초, 3.33/초/서버 당</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>로그 아웃 속도:</p>
<ul>
<li><p>총 10 개/초, 3.33/초/서버 당</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>채팅 속도:</p>
<ul>
<li><p>서버 당 총 20 개/초, 6.66/초</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 다음 성능 카운터 번호는 다양 한 하드웨어 사양 또는 사용자 프로필을 사용할 때 다를 수 있습니다.



</div>

### <a name="performance-counter-to-be-monitored"></a>모니터링할 성능 카운터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>성능 카운터</th>
<th>하나만</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>프로세스 (ChannelService)-&gt;% 프로세서 시간</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

