---
title: 'Lync Server 2013: 회의, 응용 프로그램 및 중재 서버에 대 한 포트 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Lync Server 2013에서 회의, 응용 프로그램 및 중재 서버에 대 한 포트 범위 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-04-30_

QoS(서비스 품질)를 구현하기 위해서는 회의, 응용 프로그램 및 중재 서버에서 오디오, 비디오 및 응용 프로그램 공유에 대한 동일한 포트 범위를 구성해야 합니다. 또한 이러한 포트 범위는 어떠한 방식으로든 서로 겹쳐서는 안됩니다. 간단한 예로, 회의 서버에서 비디오를 위해 10000~10999 포트를 사용한다고 가정해보십시오. 이 경우에는 응용 프로그램 및 중재 서버에서도 10000~10999 포트를 비디오용으로 예약해야 합니다. 그렇지 않으면 QoS가 예상한 대로 작동하지 않습니다.

이와 비슷하게, 10000~10999 포트를 비디오용으로 예약하지만 10500~11999 포트는 오디오용으로 예약한다고 가정해보십시오. 이 경우에는 포트 범위가 겹치기 때문에 QoS(서비스 품질) 문제가 발생할 수 있습니다. QoS에서는 각 형식이 고유한 포트 집합을 가져야 합니다. 10000~10999 포트를 비디오용으로 사용한다면 다른 범위를 사용해야 합니다(예: 오디오에 11000~11999 사용).

기본적으로 오디오 및 비디오 포트 범위는 Microsoft Lync Server 2013에서 중복 되지 않습니다. 그러나 응용 프로그램 공유에 할당 된 포트 범위가 오디오 및 비디오 포트 범위와 겹칩니다. (즉, 이러한 범위는 고유 하지 않을 수 있습니다.) Lync Server 2013 관리 셸에서 다음 세 명령을 실행 하 여 회의, 응용 프로그램 및 중재 서버에 대 한 기존 포트 범위를 확인할 수 있습니다.

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 앞의 명령에서 볼 수 있듯이, 각 포트 유형(오디오, 비디오 및 응용 프로그램 공유)에는 두 개의 개별 속성 값인 포트 시작 및 포트 개수 값이 지정됩니다. 포트 시작은 해당 형식에 사용되는 첫 번째 포트를 나타냅니다. 예를 들어 오디오 포트 시작이 50000이면 오디오 트래픽에 사용되는 첫 번째 포트가 포트 50000입니다. 오디오 포트 개수가 2(올바른 값은 아니지만 설명을 위해 사용됨)이면 오디오에 2개의 포트만 지정됩니다. 첫 번째 포트가 포트 50000이고 총 2개의 포트만 있으므로 두 번째 포트는 포트 50001이어야 합니다(포트 범위는 연속되어야 함). 따라서 오디오에 대한 포트 범위는 50000~50001까지입니다.<BR>응용 프로그램 서버 및 중재 서버는 오디오에 대해서만 QoS를 지원합니다. 응용 프로그램 서버 또는 중재 서버에서는 비디오 또는 응용 프로그램 공유 포트를 변경할 필요가 없습니다.



</div>

앞의 세 명령을 실행 하면 Lync Server 2013의 기본 포트 값이 다음과 같이 구성 된 것을 알 수 있습니다.


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


앞에서 설명한 대로 QoS 용 Lync Server 포트를 구성 하는 경우, 1) 사용자의 회의, 응용 프로그램 및 중재 서버에서 오디오 포트 설정이 동일 해야 합니다. 2) 포트 범위가 겹치지 않습니다. 위의 표를 자세히 살펴보면 3 개의 서버 유형에 대해 포트 범위가 동일 하다는 것을 알 수 있습니다. 예를 들어 시작 오디오 포트는 각 서버 유형에 대해 포트 49152로 설정 되 고 각 서버의 오디오에 대해 예약 된 총 포트 수는 8348 동일 합니다. 그러나 포트 범위가 겹치면 오디오 포트는 포트 49152에서 시작 되지만 응용 프로그램을 공유 하기 위해 포트를 별도로 설정 합니다. 서비스 품질을 최적의 상태로 사용 하기 위해서는 응용 프로그램 공유를 고유한 포트 범위를 사용 하도록 다시 구성 해야 합니다. 예를 들어 포트 40803에서 시작 하 고 8348 포트를 사용 하도록 응용 프로그램 공유를 구성할 수 있습니다. (8348 포트가 있습니까? 이러한 값을 함께 추가 하는 경우--40803 + 8348----이를 통해 응용 프로그램 공유는 포트 49150을 통해 포트 40803을 사용 합니다. 오디오 포트는 포트 49152까지 시작 되지 않으므로 겹치는 포트 범위가 더 이상 없습니다.

응용 프로그램 공유에 대해 새 포트 범위를 선택한 후에는 Set-CsConferencingServer cmdlet을 사용하여 항목을 변경할 수 있습니다. 이러한 서버에서 응용 프로그램 공유 트래픽이 처리되지 않기 때문에 이러한 항목은 응용 프로그램 서버 또는 중재 서버에서 변경할 필요가 없습니다. 오디오 트래픽에 사용되는 포트를 다시 지정할 경우에만 해당 서버에서 포트 값을 변경해야 합니다.

단일 회의 서버에서 응용 프로그램 공유에 대 한 포트 값을 수정 하려면 Lync Server 관리 셸에서와 비슷한 명령을 실행 합니다.

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

모든 회의 서버에서 이러한 항목을 변경하려는 경우 대신 다음 명령을 실행할 수 있습니다.

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

포트 설정을 변경한 후에는 변경 내용의 영향을 받는 각 서비스를 중지하고 다시 시작해야 합니다.

회의 서버, 응용 프로그램 서버 및 중재 서버가 정확히 동일한 포트 범위를 공유할 필요는 없으며, 모든 서버에서 고유한 포트 범위를 별도로 설정하기만 하면 됩니다. 하지만 관리 측면에서는 모든 서버에서 동일한 포트 집합을 사용하는 것이 더 쉬울 것입니다.

</div>

<span> </span>

</div>

</div>

</div>

