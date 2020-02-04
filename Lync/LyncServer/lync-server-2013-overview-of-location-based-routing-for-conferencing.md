---
title: 'Lync Server 2013: 위치 기반 회의에 대 한 라우팅 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 회의를 위한 위치 기반 라우팅 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-19_

위치 기반 라우팅 회의 응용 프로그램은 PSTN 유료 바이패스를 방지 하기 위한 메커니즘을 Lync 컨퍼런스에 제공 합니다. 이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 Lync 사용자의 위치를 기반으로 위치 기반 라우팅 제한을 적용 합니다.

위치 기반 라우팅 회의 응용 프로그램에서는 다음 조건이 충족 되는 경우 Lync 모임에 위치 기반 라우팅이 적용 되는지 여부를 결정 합니다.

  - 모임 이끌이는 위치 기반 회람을 사용할 수 있습니다. 위치 기반 라우팅 제한은 위치 기반 라우팅을 사용 하도록 설정 된 사용자가 구성한 회의에만 적용 됩니다.

  - 하나 이상의 모임 참가자가 PSTN 끝점입니다. 위치 기반 라우팅 제한은 PSTN 끝점을 포함 하는 회의에만 적용할 수 있습니다.

  - PSTN에 전화를 연결 하는 데 사용 되는 PSTN 게이트웨이는 물론 이끌이와 참가자가 연결 되는 네트워크 사이트에 대 한 네트워크 사이트를 찾습니다.

위치 기반 라우팅 회의 응용 프로그램을 사용 하면 다른 네트워크 사이트의 Lync 사용자 및 PSTN 끝점을 같은 회의에 참가 시킬 수 없습니다. 모임 이끌이가 위치 기반 회람을 사용 하도록 설정 되어 있는 경우 회의 응용 프로그램에서 다음 제한 사항이 적용 됩니다.

  - Lync 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가 한 끝점에 따라 다르며,이 제한은 참가 한 끝점 종료 및 새 끝점이 회의에 참가 함에 따라 조정 됩니다. 이끌이 및 참가자가 같은 네트워크 사이트에서 Lync 모임에 참가 하는 경우 PSTN 끝점, 같은 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트의 다른 참가자 또는 알 수 없는 네트워크 사이트의 참가자가 사용할 수 있습니다. 합류.

  - 이끌이 및 참가자가 서로 다른 네트워크나 알 수 없는 네트워크 사이트에서 모임에 참가 하는 경우 PSTN 호출이 위치 기반 라우팅에 대해 사용 하도록 설정 된 SIP 트렁크의 ingresses에서 모임에 참가할 수 없습니다.

  - 이끌이 및 참가자가 모두 동일한 네트워크 사이트의 모임에 참가 하 고 있으며 PSTN에서 같은 모임에 참가 하는 참가자가 있는 경우 다른 네트워크 사이트의 Lync 끝점은 모임에 참가할 수 없습니다.

이러한 회의 위치 기반 라우팅 제한은 다음 표에 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>지정 된 시점에 회의의 사용자</p></td>
<td><p>회의에 참가할 수 있는 사용자 (들)</p></td>
<td><p>사용자가 회의에 참가할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p>
<p>PSTN 끝점에서 참가 하는 사용자</p></td>
<td><p>없음</p></td>
</tr>
<tr class="odd">
<td><p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>모든 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
<td><p>PSTN 끝점을 통해 참가 하는 사용자</p></td>
</tr>
<tr class="even">
<td><p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
<td><p>PSTN 끝점을 통해 참가 하는 사용자</p></td>
</tr>
<tr class="odd">
<td><p>단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자 및 PSTN 끝점에서 참가 하는 사용자</p></td>
<td><p>동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
</tr>
</tbody>
</table>


다음은 위치 기반 라우팅 회의 응용 프로그램의 추가 특성입니다.

  - 사용자가 전화 회의에 참가할 수 없는 경우에는 회의에 대 한 사용자 통화가 거부 되 고 Lync 클라이언트에서 통화가 완료 되지 않았거나 종료 되었음을 보고 합니다.

  - 위치 기반 라우팅 enforcements를 사용 하 여 전화 회의에 참가 하는 PSTN 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 트렁크를 통해 끝점에 참가 하는 경우 상태에 관계 없이 전화 회의에 참가 하도록 제한 되지 않습니다.

  - PSTN으로 호출 되지 않는 SIP 트렁크를 통해 Mediations 서버에 연결 된 PBX 시스템은 SIP 트렁크가 정의 된 동일한 네트워크 사이트에 있는 Lync 사용자와 동일한 enforcements를 갖습니다. 예를 들어 PSTN 끝점은 PBX 사용자와 Lync 사용자 (동일한 네트워크 사이트에 있는 경우)와 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 Lync 사용자가 아닌 다른 네트워크 사이트에 있는 경우 PSTN 종점이 전화 회의에 참가할 수 없게 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

