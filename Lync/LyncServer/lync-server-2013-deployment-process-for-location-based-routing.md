---
title: 'Lync Server 2013: 위치 기반 라우팅 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 위치 기반 라우팅 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

이 항목에서는 위치 기반 라우팅 구성과 관련 된 프로세스에 대 한 개요를 제공 합니다. 위치 기반 라우팅을 구성 하기 전에 Lync Server Enterprise Edition 또는 Standard Edition을 Enterprise Voice와 함께 배포 해야 합니다. 엔터프라이즈 음성을 배포할 때 위치 기반 라우팅에 필요한 구성 요소가 이미 설치 되어 있고 사용 하도록 설정 되어 있습니다.

### <a name="location-based-routing-deployment-process"></a>위치 기반 라우팅 배포 프로세스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>필수 그룹 및 역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Enterprise Voice 배포</p></td>
<td><ul>
<li><p>트렁크 구성</p></li>
<li><p>음성 정책 만들기</p></li>
<li><p>음성 경로 정의</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Enterprise Voice 배포</p></td>
</tr>
<tr class="even">
<td><p>Enterprise Voice 배포 확인</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>네트워크 지역, 사이트 및 서브넷 구성</p></td>
<td><ul>
<li><p>네트워크 지역 만들기</p></li>
<li><p>네트워크 사이트 만들기</p></li>
<li><p>서브넷을 네트워크 사이트와 연결</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>네트워크 지역, 사이트 및 서브넷 정보<br />
네트워크 지역 만들기 또는 수정<br />
네트워크 사이트 만들기 또는 수정<br />
네트워크 사이트에 서브넷 연결</p></td>
</tr>
<tr class="even">
<td><p>위치 기반 라우팅 구성</p></td>
<td><ul>
<li><p>음성 라우팅 정책 만들기</p></li>
<li><p>트렁크 별로 별도의 트렁크 구성 정의</p></li>
<li><p>음성 정책 수정</p></li>
<li><p>위치 기반 라우팅 구성 사용</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>샘플 배포

다음 배포는 위치 기반 라우팅을 통해 사용 가능한 메커니즘을 추가로 보여 주기 위해 사용 됩니다.

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>들어오는 PSTN 통화

관리자는 위치 기반 라우팅으로 "사이트 1 게이트웨이"로 통화를 라우팅하기 위해 정의 된 트렁크를 사용 하도록 설정 하 고, 사이트 1에 "사이트 1 게이트웨이"를 연결할 수 있습니다. "사이트 1 게이트웨이"를 통해 라우팅되는 통화는 사이트 1에 있는 사용자 에게만 라우팅됩니다. PSTN 전화 바이패스를 방지 하기 위해 사이트 2와 같이 다른 사이트의 사용자에 게 전송 되는 "사이트 1 게이트웨이"를 통해 라우팅되는 모든 호출이 차단 됩니다.

"Site 1 Gateway"를 통한 모든 수신 PSTN 통화는 사이트 1에 있는 끝점 으로만 라우팅할 수 있습니다. 예를 들어 "Lync 사용자 1"이 사이트 2로 이동 하는 경우 "Site 1 Gateway"를 통한 모든 수신 PSTN 전화를 사이트 2에 있는 "Lync 사용자 1" 끝점으로 라우팅되지 않습니다. "Lync 사용자 1"이 사용자의 위치를 확인할 수 없는 알 수 없는 네트워크 사이트에 연결 되어 있는 경우에도 동일한 라우팅 규칙이 적용 됩니다.

다음 표에서는이 컨텍스트에서 "Lync 사용자 1"의 사용자 환경에 대해 간략히 설명 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>네트워크 사이트 1에 있는 Lync 사용자 1 끝점</th>
<th>네트워크 사이트 2에 있는 Lync 사용자 1 끝점</th>
<th>Lync 사용자 1 끝점이 알 수 없는 네트워크 사이트에 있습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자 1에 대 한 인바운드 PSTN 통화</p></td>
<td><p>통화가이 위치의 끝점으로 라우팅됩니다.</p></td>
<td><p>통화가이 위치의 끝점으로 라우팅되지 않음</p></td>
<td><p>통화가이 위치의 끝점으로 라우팅되지 않음</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>나가는 PSTN 통화

음성 경로는 사용자에 게 직접 할당 된 음성 정책 및 네트워크 사이트에 할당 된 음성 라우팅 정책에서 모두 참조 됩니다. 두 정책에는 호출을 다르게 라우팅하는 데 사용할 수 있는 경로에 대 한 참조가 포함 되어 있습니다. 예를 들어 관리자는 네트워크 사이트 1에 있는 모든 사용자에 대 한 음성 라우팅 정책을 정의 하 여 모든 아웃 바운드 호출을 "사이트 1 게이트웨이"를 통해 라우팅할 수 있으며, 일부 사용자의 음성 정책은 "Site 2 Gateway"를 통해 모든 아웃 바운드 호출에 대 한 경로를 정의 합니다. 이러한 사용자는 네트워크 사이트 1에 있고, 아웃 바운드 통화는 "사이트 1 게이트웨이"를 통해 라우팅됩니다.

사용자가 위치 기반 라우팅을 위해 구성 된 네트워크 사이트에 있는 경우 네트워크 사이트의 음성 라우팅 정책 경로가 사용자의 음성 정책 경로를 재정의 합니다. 이 규칙은 특히 다른 사이트로 일시적으로 이동 하는 사용자에 게 유용 합니다. 이 경우 사용자는 항상 해당 지역의 로컬 게이트웨이를 사용 합니다. "Lync 사용자 3"이 "사이트 2"에 있는 경우 모든 아웃 바운드 통화는 "Site 2 Gateway"를 통해 라우팅되고, 사이트 1로 이동 하는 경우 사이트 1에 있는 모든 아웃 바운드 통화는 "Site 1 Gateway"를 통해 라우팅됩니다.

다음 표에서는 Lync 사용자 1이 다음 네트워크 사이트에서 아웃 바운드 호출을 수행 하는 사용자 환경을 보여 줍니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>네트워크 사이트 1</th>
<th>네트워크 사이트 2</th>
<th>알 수 없는 네트워크 사이트 또는 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>아웃 바운드 호출 권한 부여</p></td>
<td><p>Lync 사용자 1 음성 정책</p></td>
<td><p>Lync 사용자 1 음성 정책</p></td>
<td><p>Lync 사용자 1 음성 정책</p></td>
</tr>
<tr class="even">
<td><p>아웃 바운드 통화 라우팅</p></td>
<td><p>사이트 1 음성 라우팅 정책</p></td>
<td><p>사이트 2 음성 라우팅 정책</p></td>
<td><p>사용자의 음성 정책 및 위치 기반 라우팅을 사용 하도록 설정 되지 않은 시스템에만 해당</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>통화 전송 및 전달

통화가 전송 되거나 전달 되 면 통화 라우팅은 위치 기반 라우팅을 통해 영향을 받습니다.

다음 표에서는 Lync 사용자 1이 PSTN 통화를 다른 Lync 사용자에 게 전송 하거나 전달 하는 방법을 보여 줍니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자가 착신 전환 또는 전달 시작</th>
<th>Lync 사용자 2</th>
<th>Lync 사용자 4</th>
<th>네트워크 사이트의 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자 1</p></td>
<td><p>착신 전환 또는 전송이 허용 됨</p></td>
<td><p>착신 전환 또는 전송이 허용 되지 않음</p></td>
<td><p>착신 전환 또는 전송이 허용 되지 않음</p></td>
</tr>
</tbody>
</table>

  
다음 표에서는 위치 기반 라우팅이 전송 되는 Lync 사용자의 위치 (Lync user 2, Lync 사용자 4 등)를 PSTN 끝점으로 이동 하는 방법에 따라 호출이 라우팅되는 방식에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>통화가 전송 되거나 전달 되는 끝점</th>
<th>Lync 사용자 2</th>
<th>Lync 사용자 4</th>
<th>네트워크 사이트의 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 끝점</p></td>
<td><p>착신 전환 또는 전송은 사이트 1 음성 라우팅 정책을 통해 라우팅되고 사이트 1 게이트웨이를 통해 송신 됩니다.</p></td>
<td><p>착신 전환 또는 전송은 사이트 2 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 egress를 통해 라우팅됩니다.</p></td>
<td><p>위치 기반 라우팅을 사용 하도록 설정 되지 않은 게이트웨이를 통해 착신 전환 또는 전송이 Lync 사용자 음성 정책을 통과 하 고 송신 됩니다 (사용 가능한 경우).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>동시 벨 울림

샘플 토폴로지에서 위치 기반 라우팅을 구성한 후에는 다음과 같은 상호 작용이 적용 됩니다.

다음 표에서는 위치 기반 라우팅이 다른 Lync 사용자에 대 한 동시 신호음을 허용 하는지 여부를 보여 줍니다 (예: Lync user 2, Lync 사용자 4 등).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>들어오는 PSTN 통화 대상</th>
<th>Lync 사용자 2</th>
<th>Lync 사용자 4</th>
<th>네트워크 사이트의 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자 1</p></td>
<td><p>동시 신호음 허용</p></td>
<td><p>동시 벨 울림은 허용 되지 않습니다.</p></td>
<td><p>동시 벨 울림은 허용 되지 않습니다.</p></td>
</tr>
</tbody>
</table>

  
다음 표에서는 위치 기반 라우팅이 다른 Lync 사용자의 PSTN 끝점으로 동시 신호음을 허용 하는지 여부를 보여 줍니다 (예: Lync user 2, Lync 사용자 4 등).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>동시 링 대상</th>
<th>Lync 사용자 2</th>
<th>Lync 사용자 4</th>
<th>네트워크 사이트의 Lync 사용자가 위치 기반 라우팅을 사용 하도록 설정 되지 않음</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 사용자 1 휴대폰 (PSTN 끝점)</p></td>
<td><p>네트워크 사이트 1의 음성 라우팅 정책 및 사이트 1 게이트웨이를 통해 송신 된 통화</p></td>
<td><p>네트워크 사이트 2의 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 송신 된 통화</p></td>
<td><p>전화 건 사람이 발신자 음성 정책을 통해 라우팅되고, 위치 기반 라우팅을 사용 하도록 설정 되지 않은 PSTN 게이트웨이를 통해 egress 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

