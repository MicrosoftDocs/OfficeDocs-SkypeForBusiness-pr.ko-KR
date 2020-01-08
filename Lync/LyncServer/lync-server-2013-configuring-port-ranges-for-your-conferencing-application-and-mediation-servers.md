---
title: 'Lync Server 2013: 회의, 응용 프로그램 및 중재 서버에 대 한 포트 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Lync Server 2013에서 회의, 응용 프로그램 및 중재 서버용 포트 범위 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-04-30_

서비스 품질을 구현 하려면, 회의, 응용 프로그램, 중재 서버에서 오디오, 비디오, 응용 프로그램 공유에 대해 동일한 포트 범위를 구성 해야 합니다. 또한 이러한 포트 범위는 어떤 방식으로든 중복 되지 않아야 합니다. 간단한 예제를 사용 하려면 회의 서버의 비디오에 대해 포트 1만 ~ 10999을 (를) 사용 한다고 가정 합니다. 즉, 응용 프로그램 및 중재 서버에서 비디오를 위해 1만 ~ 10999 포트를 예약 해야 합니다. 그렇지 않으면 QoS가 예상 대로 작동 하지 않습니다.

마찬가지로 비디오용으로 포트 1만 ~ 10999을 예약 하 고 오디오에 대해 포트 10500 ~ 11999을 예약 한다고 가정 합니다. 이렇게 하면 포트 범위가 겹치게 되므로 서비스 품질에 대 한 문제가 발생할 수 있습니다. QoS를 사용 하는 경우 각 모달 포트는 고유한 포트 집합을 사용 해야 합니다. 비디오에 1만 ~ 10999을 사용할 경우 다른 범위를 사용 해야 합니다 (예를 들어 11000 ~ 11999 (오디오)).

기본적으로 Microsoft Lync Server 2013에서 오디오 및 비디오 포트 범위가 중복 되지 않습니다. 그러나 오디오 및 비디오 포트 범위와 응용 프로그램 공유에 할당 된 포트 범위가 겹칩니다. 즉, 이러한 범위 중 어느 것도 고유 하지 않음을 의미 합니다. Lync Server 2013 관리 셸에서 다음 세 개의 명령을 실행 하 여 회의, 응용 프로그램 및 중재 서버의 기존 포트 범위를 확인할 수 있습니다.

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 앞의 명령에서 볼 수 있듯이 각 포트 유형-오디오, 비디오 및 응용 프로그램 공유에는 두 가지 개별 속성 값인 포트 시작 및 포트 카운트가 할당 됩니다. 포트 시작은 해당 모달에 사용 되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 5만와 같으면 오디오 트래픽에 사용 되는 첫 번째 포트가 포트 5만입니다. 오디오 포트 카운트가 2 (유효한 값이 아니지만 여기에서 설명 하는 데 사용 됨) 인 경우 오디오에 대해 2 개의 포트만 할당 한다는 의미입니다. 첫 번째 포트가 포트 5만이 고 총 두 개의 포트가 있는 경우 두 번째 포트는 포트 50001 (포트 범위는 연속적 이어야 함) 이어야 합니다. 결과적으로 오디오의 포트 범위는 포트 5만 ~ 50001 (포함)입니다.<BR>단, 응용 프로그램 서버와 중재 서버는 오디오에 대 한 QoS만 지원 합니다. 응용 프로그램 서버나 중재 서버에서 비디오 또는 응용 프로그램 공유 포트를 변경할 필요는 없습니다.



</div>

앞의 세 명령을 실행 하는 경우 Lync Server 2013의 기본 포트 값이 다음과 같이 구성 되어 있는 것을 확인할 수 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>속성</th>
<th>회의 서버</th>
<th>응용 프로그램 서버</th>
<th>중재 서버</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


앞에서 설명한 대로 QoS 용 Lync Server 포트를 구성 하는 경우 다음을 수행 해야 합니다. 1) 오디오 포트 설정이 내 회의, 응용 프로그램, 중재 서버에서 동일 하 게 유지 됩니다. and, 2) 포트 범위가 중복 되지 않습니다. 앞의 표에서 자세히 보면 포트 범위가 세 가지 서버 유형 모두와 동일 하다는 것을 알 수 있습니다. 예를 들어 시작 오디오 포트는 각 서버 유형에 서 포트 49152로 설정 되 고 각 서버에서 오디오에 대해 예약 된 총 포트 수는 동일 합니다 (8348). 그러나 포트 범위가 겹치지만 오디오 포트는 포트 49152에서 시작 하지만, 포트는 응용 프로그램 공유에 대해 별도로 설정 됩니다. 서비스 품질을 최적화 하기 위해 고유한 포트 범위를 사용 하도록 응용 프로그램 공유를 다시 구성 해야 합니다. 예를 들어 포트 40803에서 시작 하 고 8348 포트를 사용 하도록 응용 프로그램 공유를 구성할 수 있습니다. (8348 포트가 있는 이유는 무엇 인가요? 이러한 값을 함께 추가 하는 경우--40803 + 8348--이는 응용 프로그램 공유가 포트 49150를 통해 포트 40803를 사용 하는 것을 의미 합니다. 오디오 포트는 포트 49152까지 시작 되지 않으므로 겹치는 포트 범위가 더 이상 없습니다.

응용 프로그램 공유에 대 한 새 포트 범위를 선택한 후에는 CsConferencingServer cmdlet을 사용 하 여 변경할 수 있습니다. 이러한 서버는 응용 프로그램 서버나 중재 서버에서는 이러한 변경 작업을 수행할 필요가 없습니다. 오디오 트래픽에 사용 되는 포트를 다시 할당 하기로 결정 한 경우에만 이러한 서버에서 포트 값을 변경 해야 합니다.

단일 회의 서버에서 응용 프로그램 공유에 대 한 포트 값을 수정 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

모든 회의 서버에서 이러한 변경 작업을 수행 하려면이 명령을 대신 실행할 수 있습니다.

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

포트 설정을 변경한 후 변경 내용에 따라 영향을 받는 각 서비스를 중지 한 다음 다시 시작 해야 합니다.

사용자의 회의 서버, 응용 프로그램 서버, 중재 서버는 똑같은 포트 범위를 공유 하도록 필수가 아닙니다. 유일한 이유는 모든 서버에 고유한 포트 범위를 별도로 설정 하는 것입니다. 그러나 모든 서버에서 동일한 포트 집합을 사용 하는 경우에는 일반적으로 관리 하기가 더 쉽습니다.

</div>

<span> </span>

</div>

</div>

</div>

