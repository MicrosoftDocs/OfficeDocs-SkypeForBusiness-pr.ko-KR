---
title: Lync Server 2013:에 지 서버에 대 한 포트 범위 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce17300c6504989d132cb27301128bfbc568870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Lync Server 2013에서에 지 서버에 대 한 포트 범위 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-07-24_

에 지 서버를 사용 하면 오디오, 비디오 및 응용 프로그램 공유에 대해 별도의 포트 범위를 구성할 필요가 없습니다. 마찬가지로에 지 서버에 사용 되는 포트 범위가 회의, 응용 프로그램 및 중재 서버에 사용 되는 포트 범위와 일치 하지 않아도 됩니다. 이 예를 계속 진행 하기 전에이 옵션을 사용 하는 것이 좋지만,이 경우에는 포트 범위를 변경 하지 않는 것이 좋으며,이는 5만 포트 범위의 외부로 이동할 경우 일부 시나리오에 부정적인 영향을 줄 수 있다는 것입니다.

예를 들어 다음과 같은 포트 범위를 사용 하도록 회의, 응용 프로그램 및 중재 서버를 구성 했다고 가정 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>패킷 종류</th>
<th>시작 포트</th>
<th>예약 된 포트 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>오디오만</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>비디오</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>합계</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


여기에서 볼 수 있듯이 오디오, 비디오 및 응용 프로그램 공유를 위한 포트 범위는 포트 40803에서 시작 하 고 총 24732 포트를 포함 합니다. 원하는 경우에는 Lync Server 관리 셸에서와 비슷한 명령을 실행 하 여 이러한 전체 포트 값을 사용 하도록 해당에 지 서버를 구성할 수 있습니다.

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

또는 다음 명령을 사용 하 여 조직에 있는 모든에 지 서버를 동시에 구성 합니다.

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

다음 Lync Server 관리 셸 명령을 사용 하 여에 지 서버에 대 한 현재 포트 설정을 확인할 수 있습니다.

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

다시 말하지만, 이러한 옵션을 제공 하는 경우에는 포트 구성의 경우를 그대로 유지 하는 것이 좋습니다.

</div>

<span> </span>

</div>

</div>

</div>

