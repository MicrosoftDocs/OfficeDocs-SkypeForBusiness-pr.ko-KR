---
title: 'Lync Server 2013: DNS 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

다음 표에는 하드웨어 부하 분산 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다. 디렉터 역할에는 프런트 엔드 서버로 유사한 DNS 레코드가 필요 합니다. 필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다. 프런트 엔드 서버와 달리 디렉터 풀은 사용자 계정을 호스팅하거나 모바일 서비스를 호스트 하지 않습니다.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>하드웨어 부하 분산 장치 및 DNS 부하 분산을 사용 하는 디렉터 풀에 필요한 DNS 레코드

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>위치/형식/포트</th>
<th>FQDN/DNS 레코드</th>
<th>IP 주소/FQDN</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>복제 및 서버에서 서버에 통신 하는 데 사용 되는 디렉터 호스트 레코드</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>디렉터 풀 HLB VIP</p></td>
<td><p>DNS 부하 분산 디렉터 풀에 대 한 호스트 레코드</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>디렉터 풀 HLB VIP</p></td>
<td><p>Edge 서버의 내부 인터페이스에 있는 SIP (인바운드 세션 초기화 프로토콜)</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>디렉터 풀 HLB VIP</p></td>
<td><p>리버스 프록시에서 하드웨어 부하 분산 된 전화 접속 웹 서비스를 게시 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>디렉터 풀 HLB VIP</p></td>
<td><p>리버스 프록시에서 웹 서비스에 대 한 하드웨어 부하 분산 게시</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>디렉터 풀 HLB VIP</p></td>
<td><p>디렉터 풀에 대 한 역방향 프록시 웹 티켓이 외부 웹 서비스에 의해 게시 되 고 정의 된 하드웨어 부하 분산</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

