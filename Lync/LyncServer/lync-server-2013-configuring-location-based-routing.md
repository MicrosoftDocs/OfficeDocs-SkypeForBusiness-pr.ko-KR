---
title: 'Lync Server 2013: Location-Based 라우팅 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517421"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Lync Server 2013에서 Location-Based 라우팅 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-12_

Lync Server 2013 C U 1 Location-Based 라우팅은 Enterprise Voice의 기능입니다. Location-Based 라우팅은 Lync Server 2013 C U 1에서 호출을 라우팅하는 방법을 제어 하는 통화 관리 기능입니다. Lync 발신자의 위치에 따라 통화를 PBX 또는 PSTN 대상으로 라우팅할 수 있는지 여부에 대 한 제한을 적용 합니다. Location-Based 라우팅은 발신자의 네트워크 위치를 기반으로 PSTN 통화에 통화 권한 부여 규칙을 적용 합니다. 발신자의 위치는 발신자가 연결 되는 네트워크 서브넷과 연결 된 네트워크 사이트를 기반으로 결정 됩니다. Location-Based 라우팅을 구성 하려면 먼저 Enterprise Voice를 배포한 다음 네트워크 지역, 사이트 및 서브넷을 구성 해야 합니다. 이렇게 하면 Location-Based 라우팅을 사용 하기 위한 토대를 설정 합니다.

Location-Based 라우팅을 배포 하기 전에 먼저 Enterprise Voice를 배포 하 고 네트워크 지역 및 사이트를 구성 하 고 네트워크 사이트에 네트워크 서브넷을 연결 해야 합니다. 완료 되 면 Location-Based 라우팅을 구성할 수 있습니다. 네트워크 지역, 사이트 및 서브넷을 구성 하는 방법에 대 한 단계는 [Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.

이 섹션에서는 다음 예제를 그림으로 사용 하 여 Location-Based 라우팅을 구성 하는 과정을 안내 합니다.

![Enterprise Voice 위치 기반 라우팅 예](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 위치 기반 라우팅 예")

  
다음 표에서는이 예제에 정의 된 사용자를 나타냅니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>끝점 유형</th>
<th>위치</th>
<th>사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>뉴델리 회사 사무실</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 회사 사무실</p></td>
<td><p>HYD-1, HYD-2, HYD-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>알 수 없음 (예: 호텔)</p></td>
<td><p>UNK-1</p></td>
</tr>
<tr class="even">
<td><p>전화가</p></td>
<td><p>뉴델리 회사 사무실</p></td>
<td><p>DEL-PBX-1, DEL-2</p></td>
</tr>
<tr class="odd">
<td><p>전화가</p></td>
<td><p>Hyderabad 회사 사무실</p></td>
<td><p>HYD-1, HYD-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>알 수 없음</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

다음 표에서는이 예제 환경에 설명 된 시스템을 보여 줍니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>컴퓨터</th>
<th>위치</th>
<th>이름</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 C U 1 풀</p></td>
<td><p>그</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 C U 1, 중재 서버</p></td>
<td><p>그</p></td>
<td><p>PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 게이트웨이 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 게이트웨이 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>적색-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Enterprise Voice 구성](lync-server-2013-configuring-enterprise-voice.md)

  - [Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Lync Server 2013에서 Location-Based 라우팅 사용](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

