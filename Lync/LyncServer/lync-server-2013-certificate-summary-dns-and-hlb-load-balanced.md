---
title: 'Lync Server 2013: 인증서 요약 - DNS 및 HLB 부하 분산됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>인증서 요약 - Lync Server 2013에서 DNS 및 HLB 부하 분산됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

DNS 부하 분산이 있는 디렉터에 대 한 인증서 요구 사항과 하드웨어 로드 균형 조정기는 디렉터에서 수신할 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다. 풀의 각 디렉터에 대 한 인증서가 요청 됩니다. 하드웨어 로드 균형 조정기는 역방향 프록시의 트래픽에만 로드 균형을 조정 한다는 점에 유의 해야 합니다. 또한 각 서버에 설치 된 서버 대 서버 인증 용도의 OAuth 토큰 인증서가 있습니다.

### <a name="certificates-for-director"></a>디렉터에 대 한 인증서

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
<p>디렉터는 주변 서버나 Edge 서버의 역방향 프록시 요청에 응답 합니다. 내부 클라이언트는 디렉터를 사용 하지 않습니다.</p>
<p>또는 간단한 Url의 와일드 카드 항목</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>입력 내용 없음</p></td>
<td><div>

> [!IMPORTANT]  
> 최소 키 길이는 1024 이지만 최소 권장 키 길이는 2048 비트 라고 알리는 경고가 표시 될 수 있습니다.


</div>
<p>OAuthTokenIssuer 인증서는 대규모 환경에서 서버를 인증 하기 위한 용도로만 사용할 수 있는 단일 용도의 인증서 이며, 내부 CA 또는 공용 CA에서 요청을 받아야 합니다. 인증서가 필요 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

