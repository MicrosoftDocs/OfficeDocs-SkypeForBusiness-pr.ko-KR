---
title: 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcecbd1ec0c486e888a8c7303e450f75abf05bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013의 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

하드웨어 로드 균형 조정기를 사용 하는 디렉터에 대 한 인증서 요구 사항은 디렉터 풀이 받을 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다. 풀의 각 디렉터에 대 한 인증서가 요청 됩니다. 또한 각 서버에 설치 된 서버 대 서버 인증 용도의 OAuth 토큰 인증서가 있습니다.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>하드웨어 부하 분산 장치를 사용 하 여 확장 된 디렉터에 대 한 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>주체 이름 (SN)</th>
<th>주제 대체 이름 (SAN)</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(선택적) *. contoso.com</p></td>
<td><p>디렉터 인증서는 내부에서 관리 하는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</p>
<p>디렉터는 주변 서버나 Edge 서버의 역방향 프록시 요청에 응답 합니다.</p>
<p>또는 간단한 Url의 와일드 카드 항목</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>입력 내용 없음</p></td>
<td>


> [!IMPORTANT]
> 최소 키 길이는 1024 이지만 최소 권장 키 길이는 2048 비트 라고 알리는 경고가 표시 될 수 있습니다.


<p>OAuthTokenIssuer 인증서는 대규모 환경에서 서버를 인증 하기 위한 용도로만 사용할 수 있는 단일 용도의 인증서 이며, 내부 CA 또는 공용 CA에서 요청을 받아야 합니다. 인증서가 필요 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

