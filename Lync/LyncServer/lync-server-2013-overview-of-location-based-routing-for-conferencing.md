---
title: 'Lync Server 2013: 회의의 Location-Based 라우팅 개요'
description: 'Lync Server 2013: 회의의 Location-Based 라우팅에 대 한 개요입니다.'
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
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577374"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의에 대 한 Location-Based 라우팅 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-19_

Location-Based 라우팅 회의 응용 프로그램은 PSTN 전화 바이패스를 방지 하기 위한 메커니즘을 Lync 회의에 제공 합니다. 이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 Lync 사용자의 위치에 따라 Location-Based 라우팅 제한을 적용 합니다.

Location-Based 라우팅 회의 응용 프로그램은 다음 조건이 충족 될 경우 Lync 모임에서 Location-Based 라우팅을 적용할지 여부를 결정 합니다.

  - 모임 이끌이가 Location-Based 라우팅을 사용할 수 있습니다. Location-Based 라우팅 제한은 Location-Based 라우팅을 사용 하도록 설정 된 사용자가 구성한 전화 회의에만 적용 됩니다.

  - 하나 이상의 모임 참가자가 PSTN 끝점입니다. Location-Based 라우팅 제한은 PSTN 끝점이 포함 된 회의에만 적용 됩니다.

  - 회의를 PSTN에 연결 하는 데 사용 되는 PSTN 게이트웨이가 있는 네트워크 사이트와 이끌이 및 참가자가 연결할 네트워크 사이트입니다.

Location-Based 라우팅 회의 응용 프로그램을 통해 Lync 사용자와 PSTN 끝점이 서로 다른 네트워크 사이트에서 같은 회의에 참가 하지 못하게 합니다. 모임 이끌이가 Location-Based 라우팅을 사용 하도록 설정 되어 있으면 회의 응용 프로그램은 다음과 같은 제한을 적용 합니다.

  - Lync 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가 한 끝점에 의존 하며,이 제한은 연결 된 끝점 탈퇴 및 새 끝점이 전화 회의에 참가 하는 것으로 조정 됩니다. 이끌이 및 참가자가 동일한 네트워크 사이트에서 Lync 모임에 참가 하는 경우 PSTN 끝점, 같은 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트의 다른 참가자 또는 알 수 없는 네트워크 사이트의 참가자가 참가할 수 있습니다.

  - 이끌이 및 참가자가 다른 네트워크나 알 수 없는 네트워크 사이트에서 모임에 참가 하는 경우 PSTN 끝점이 Location-Based 라우팅을 위해 사용 하도록 설정 된 SIP 트렁크에서 전화를 ingresses 경우 모임에 참가할 수 없습니다.

  - 이끌이 및 참가자가 동일한 네트워크 사이트의 모임에 모두 참가 하 고 있고 PSTN에서 같은 모임에 참가 하는 참가자가 있는 경우 다른 네트워크 사이트의 Lync 끝점이 모임에 참가할 수 없습니다.

다음 표에는 이러한 회의 Location-Based 라우팅 제한이 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>지정 된 시점에 회의의 사용자</p></td>
<td><p>회의에 참가할 수 있는 사용자</p></td>
<td><p>사용자가 회의에 참가할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p>
<p>PSTN 끝점에서 참가 한 사용자</p></td>
<td><p>없음</p></td>
</tr>
<tr class="odd">
<td><p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>모든 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
<td><p>PSTN 끝점을 통한 사용자 참가</p></td>
</tr>
<tr class="even">
<td><p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>모든 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
<td><p>PSTN 끝점을 통한 사용자 참가</p></td>
</tr>
<tr class="odd">
<td><p>단일 네트워크 사이트 및 PSTN 끝점에서 가입한 사용자의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p></td>
<td><p>다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</p>
<p>페더레이션 Lync VoIP 클라이언트 사용자</p></td>
</tr>
</tbody>
</table>


다음은 Location-Based 라우팅 회의 응용 프로그램의 추가 특성입니다.

  - 사용자가 Location-Based 전화 회의에 참가 하도록 허용 되지 않으면 전화 회의에 대 한 통화 호출이 거부 되 고 Lync 클라이언트는 통화가 완료 되지 않았거나 종료 되었음을 보고 합니다.

  - Location-Based 라우팅 enforcements 회의에 참가 하는 PSTN 끝점은 Location-Based 라우팅에서 사용 하도록 설정 되지 않은 트렁크를 통해 끝점이 연결 되는 경우 해당 상태에 관계 없이 회의에 참가 하도록 제한 되지 않습니다.

  - PSTN으로 전화를 걸 수 없는 SIP 트렁크를 통해 Mediations 서버에 연결 된 PBX 시스템은 SIP 트렁크가 정의 된 동일한 네트워크 사이트에 있는 Lync 사용자와 동일한 enforcements을 갖게 됩니다. 예를 들어 PSTN 끝점이 동일한 네트워크 사이트에 있는 경우 PBX 사용자 및 Lync 사용자와 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 Lync 사용자와 다른 네트워크 사이트에 있는 경우 PSTN 끝점이 회의에 참가할 수 없게 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

