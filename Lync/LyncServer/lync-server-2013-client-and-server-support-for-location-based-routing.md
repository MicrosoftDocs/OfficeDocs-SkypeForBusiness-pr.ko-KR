---
title: 'Lync Server 2013: Location-Based 라우팅을 위한 클라이언트 및 서버 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529345"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 Location-Based 라우팅에 대 한 클라이언트 및 서버 지원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-06-18_

Location-Based 라우팅은 Lync Server에 의해 적용 됩니다. Lync Server는 사용자가 회사 네트워크 내에서 연결 하는 네트워크 사이트를 식별할 수 있습니다. 원격 사용자는 회사 네트워크 외부에 있기 때문에 해당 위치를 알 수 없는 것으로 간주 됩니다.

<div>

## <a name="lync-server-support"></a>Lync Server 지원

Location-Based를 라우팅 하려면 Lync Server 2013 C U 1이 지정 된 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포 되어 있어야 합니다. Lync Server 2013 C U 1가 토폴로지의 특정 Lync 구성 요소에 설치 되어 있지 않으면 Location-Based 라우팅 제한을 완전히 적용할 수 없습니다.

다음 표에는 Location-Based 라우팅에 대해 지원 되는 서버 역할 및 버전의 조합이 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>풀 버전</th>
<th>중재 서버 버전</th>
<th>지원</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 2 월 2013 누적 업데이트</p></td>
<td><p>Lync Server 2013 2 월 2013 누적 업데이트</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2 월 2013 누적 업데이트</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 2 월 2013 누적 업데이트</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2 월 2013 누적 업데이트</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>그</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>그</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>그</p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync 클라이언트 지원

다음 표에서는 Location-Based 라우팅이 지 원하는 클라이언트를 보여 줍니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 유형</th>
<th>지원</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>예</p></td>
<td><p>Lync 2013 년 2 월 2013 누적 업데이트 포함</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>예</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>아니요</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>예</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 전화 교환</p></td>
<td><p>예</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync for Windows 8</p></td>
<td><p>아니요</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 모바일 2013</p></td>
<td><p>아니요</p></td>
<td><p>Location-Based 라우팅이 사용 하도록 설정 된 사용자가 사용 하는 경우 Lync 모바일 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Lync 모바일 2010</p></td>
<td><p>예</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Lync Mobile 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 하려면 위치 기반 라우팅을 사용 하도록 설정 된 모든 사용자에 대해 IP 오디오/비디오 설정을 사용 하지 않고 모바일 정책을 할당 합니다. 모바일 정책에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>를 참조 하십시오.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Location-Based 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

