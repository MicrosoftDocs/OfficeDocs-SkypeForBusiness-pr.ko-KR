---
title: 'Lync Server 2013: 위치 기반 라우팅 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Lync Server 2013에서 위치 기반 라우팅 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-12_

Lync Server 2013 CU1 위치 기반 라우팅은 엔터프라이즈 음성의 기능입니다. 위치 기반 라우팅은 Lync Server 2013 CU1에서 통화가 라우팅되는 방법을 제어 하는 통화 관리 기능입니다. Lync 발신자의 위치를 기반으로 통화를 PBX 또는 PSTN 목적지로 라우팅할 수 있는지에 대 한 제한 사항을 적용 합니다. 위치 기반 라우팅은 호출자의 네트워크 위치를 기반으로 하는 PSTN 통화에 대 한 통화 권한 부여 규칙을 적용 합니다. 호출자의 위치는 호출자가 연결 된 네트워크 서브넷과 연결 된 네트워크 사이트를 기준으로 결정 됩니다. 위치 기반 라우팅을 구성 하려면 먼저 엔터프라이즈 음성을 구축한 다음 네트워크 지역, 사이트 및 서브넷을 구성 해야 합니다. 위치 기반 라우팅의 사용을 위한 토대를 설정 합니다.

위치 기반 라우팅을 배포 하기 전에 먼저 엔터프라이즈 음성을 배포 하 고 네트워크 지역, 사이트를 구성 하 고 네트워크 서브넷을 네트워크 사이트에 연결 해야 합니다. 완료 되 면 위치 기반 라우팅을 구성할 수 있습니다. 네트워크 지역, 사이트 및 서브넷을 구성 하는 방법에 대 한 단계는 [Lync Server 2013의 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.

이 섹션에서는 다음 예제를 사용 하 여 위치 기반 라우팅의 구성 과정을 안내 합니다.

![엔터프라이즈 음성 위치 기반 라우팅 예](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "엔터프라이즈 음성 위치 기반 라우팅 예")

  
다음 표에서는이 예제에 정의 된 사용자를 보여 줍니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>끝점 형식</th>
<th>위치</th>
<th>사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>뉴델리 기업 사무실</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 기업 사무실</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>알 수 없음 (예: 호텔)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>뉴델리 기업 사무실</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 기업 사무실</p></td>
<td><p>HYD-PBX-1, HYD-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>없는</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

다음 표는이 예제 환경에 제시 된 시스템을 나타냅니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>시스템이</th>
<th>위치</th>
<th>이름</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 풀</p></td>
<td><p>이상</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, 중재 서버</p></td>
<td><p>이상</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 게이트웨이 1</p></td>
<td><p>뉴델리</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 게이트웨이 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>뉴델리</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>빨강-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 엔터프라이즈 음성 구성](lync-server-2013-configuring-enterprise-voice.md)

  - [Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Lync Server 2013에서 위치 기반 라우팅 사용](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

