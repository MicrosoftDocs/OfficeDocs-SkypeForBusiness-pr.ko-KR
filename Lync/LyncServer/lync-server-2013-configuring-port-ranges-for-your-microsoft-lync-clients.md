---
title: 'Lync Server 2013: Microsoft Lync 클라이언트의 포트 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Lync Server 2013에서 Microsoft Lync 클라이언트에 대 한 포트 범위 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-22_

기본적으로 Lync 클라이언트 응용 프로그램은 통신 세션에 관여 했을 때 포트 1024 및 65535 간의 모든 포트를 사용할 수 있습니다. 이는 특정 포트 범위가 클라이언트에 대해 자동으로 사용 되지 않기 때문입니다. 그러나 서비스 품질을 사용 하기 위해서는 다양 한 트래픽 형식 (오디오, 비디오, 미디어, 응용 프로그램 공유 및 파일 전송)을 일련의 고유한 포트 범위에 다시 할당 해야 합니다. Set-CsConferencingConfiguration cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.

<div>


> [!NOTE]  
> 최종 사용자는 이러한 변경을 자체적으로 변경할 수 없습니다. 포트 변경은 Set-CsConferencingConfiguration cmdlet을 사용 하는 관리자만 수행할 수 있습니다.



</div>

Microsoft Lync Server 2013 관리 셸 내에서 다음 명령을 실행 하 여 현재 통신 세션에 사용 되는 포트 범위를 확인할 수 있습니다.

    Get-CsConferencingConfiguration

Lync Server 2013을 설치한 후 회의 설정을 변경 하지 않은 경우 다음 속성 값이 포함 된 정보를 다시 확인 해야 합니다.

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

앞의 출력을 자세히 살펴보면 두 가지 중요성을 확인할 수 있습니다. 먼저 ClientMediaPortRangeEnabled 속성이 False로 설정 됩니다.

    ClientMediaPortRangeEnabled : False

이 속성을 False로 설정 하면 Lync 클라이언트는 통신 세션에 포함 될 때 포트 1024 및 65535에서 사용 가능한 포트를 사용 하기 때문에 중요 합니다. 이는 다른 포트 설정 (예: ClientMediaPort 또는 ClientVideoPort)에 관계 없이 적용 됩니다. 지정 된 포트 집합으로 사용을 제한 하려는 경우 (서비스 품질을 구현 하는 데 필요한 경우) 먼저 클라이언트 미디어 포트 범위를 사용 하도록 설정 해야 합니다. 다음 Windows PowerShell 명령을 사용 하 여 수행할 수 있습니다.

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

앞의 명령을 사용 하면 회의 구성 설정의 전역 컬렉션에 대 한 클라이언트 미디어 포트 범위가 설정 됩니다. 그러나 이러한 설정은 사이트 범위 및/또는 서비스 범위 (회의 서버 서비스의 경우)에도 적용할 수 있습니다. 특정 사이트 또는 서버에 대해 클라이언트 미디어 포트 범위를 사용 하도록 설정 하려면 Set-CsConferencingConfiguration를 호출할 때 해당 사이트 또는 서버의 Id를 지정 합니다.

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

또는이 명령을 사용 하 여 모든 회의 구성 설정에 대해 포트 범위를 동시에 사용 하도록 설정할 수 있습니다.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

중요 한 두 번째 작업은 기본적으로 각 네트워크 트래픽 유형에 대해 설정 된 미디어 포트 범위가 동일 하다는 것을 보여 주는 예입니다.

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

QoS를 구현 하기 위해 이러한 각 포트 범위는 고유 해야 합니다. 예를 들어 다음과 같이 포트 범위를 구성할 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트 트래픽 형식</th>
<th>포트 시작</th>
<th>포트 범위</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>오디오</p></td>
<td><p>50020</p></td>
<td><p>명</p></td>
</tr>
<tr class="even">
<td><p>비디오만</p></td>
<td><p>58000</p></td>
<td><p>명</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>42000</p></td>
<td><p>명</p></td>
</tr>
<tr class="even">
<td><p>파일 전송</p></td>
<td><p>42020</p></td>
<td><p>명</p></td>
</tr>
</tbody>
</table>


위의 표에서 클라이언트 포트 범위는 서버에 대해 구성 된 포트 범위의 하위 집합을 나타냅니다. 예를 들어 서버에서 응용 프로그램 공유가 포트 40803 ~ 49151을 사용 하도록 구성 되었습니다. 클라이언트 컴퓨터에서 응용 프로그램 공유는 포트 42000 ~ 42019을 사용 하도록 구성 됩니다. 이는 QoS를 더욱 쉽게 관리할 수 있도록 하기 위한 것입니다. 클라이언트 포트는 서버에 사용 되는 포트의 하위 집합을 나타내지는 않습니다. (예를 들어, 클라이언트 컴퓨터에서 응용 프로그램 공유를 구성 하는 데 사용할 수 있는 포트 1만 ~ 10019을 말합니다.) 그러나 클라이언트 포트 범위를 서버 포트 범위의 하위 집합으로 만드는 것이 좋습니다.

또한, 서버에 대 한 응용 프로그램 공유에 대 한 8348 포트가 별도로 설정 되었지만 클라이언트의 응용 프로그램 공유에 대해 20 개의 포트만 따로 설정 되었다는 사실을 알 수 있습니다. 이는 권장 사항 이지만, 어려운 규칙이 아닙니다. 일반적으로 하나의 통신 세션을 나타내기 위해 사용 가능한 각 포트를 고려할 수 있습니다. 포트 범위에서 사용 가능한 100 포트가 있는 경우 해당 컴퓨터가 주어진 시간에 최대 100의 통신 세션에 참가할 수 있음을 의미 합니다. 서버는 클라이언트 보다 많은 대화에 참여 하기 때문에 클라이언트 보다 더 많은 포트를 서버에서 여는 것이 좋습니다. 클라이언트에서 응용 프로그램을 공유 하기 위해 20 포트를 별도로 설정 하면 사용자가 지정 된 디바이스의 20 개 응용 프로그램 공유 세션에 동시에 참가할 수 있습니다. 이는 대부분의 사용자에 게 충분 한지 입증 해야 합니다.

앞의 포트 범위를 다음 Lync Server 관리 셸 명령을 사용 하 여 전역 회의 구성 설정 집합에 할당할 수 있습니다.

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

또는이 명령을 사용 하 여 모든 회의 구성 설정에 대해 동일한 포트 범위를 할당 합니다.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

개별 사용자는 Lync에서 로그 오프 한 다음 다시 로그인 해야 변경 내용이 실제로 적용 됩니다.

<div>


> [!NOTE]  
> 또한 클라이언트 미디어 포트 범위를 사용 하도록 설정한 다음 단일 명령을 사용 하 여 해당 포트 범위를 할당할 수 있습니다. 예를 들면 다음과 같습니다.<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

