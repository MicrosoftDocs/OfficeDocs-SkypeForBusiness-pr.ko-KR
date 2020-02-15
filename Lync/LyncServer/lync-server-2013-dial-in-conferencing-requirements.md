---
title: Lync Server 2013 전화 접속 회의 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013의 전화 접속 회의 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-30_

Lync Server 2013 배포 프로세스를 시작 하기 전에 다음 사항에 대 한 계획을 세워야 합니다.

  - PSTN(공중 전화망) 연결에 사용할 구성

  - 전화 접속 회의 지역을 전화 접속 액세스 번호에 할당할 전략

  - 전화 회의 디렉터리를 만들 전략

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>전화 접속 PSTN 연결 계획

전화 접속 회의에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이가 필요 합니다.

중앙 사이트 또는 분기 사이트에 중재 서버를 배포할 수 있습니다. 중앙 사이트에서는 프런트 엔드 풀 또는 Standard Edition Server에서 중재 서버를 함께 배치할 하거나 독립 실행형 서버 또는 풀에 배포 하는 것이 가능 합니다. 분기 사이트에서는 중재 서버를 독립 실행형 서버 또는 Sba (survivable Branch 기기의 구성 요소로 배포할 수 있습니다.

PSTN 게이트웨이는 중앙 사이트나 분기 사이트에 배포할 수 있습니다. 분기 사이트에서 PSTN 게이트웨이는 독립 실행형 또는 Sba (survivable 분기 기기의 구성 요소 일 수 있습니다.

<div>


> [!NOTE]  
> A/V 회의 서버에서는 미디어 바이패스를 지원 하지 않으므로 전화 접속 회의에서 미디어 바이패스를 사용 하지 않습니다.



</div>

전화 접속 회의에 대 한 중재 서버 및 PSTN 게이트웨이의 구성을 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 중재 서버용 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하십시오.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>전화 접속 회의 지역 계획

전화 접속을 구성할 때 다이얼 플랜 및 전화 접속 회의 액세스 번호를 만들 수 있습니다. 다이얼 플랜은 전화 번호의 번호와 숫자 패턴을 지정하는 정규화 규칙 집합이며, 통화 라우팅을 위해 전화 번호를 표준 E.164 형식으로 변환합니다. 전화 접속 회의 액세스 번호는 참가자가 전화 회의에 참가하기 위해 전화를 거는 번호입니다.

모든 전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜과 연결되어야 합니다. 전화 접속 회의 지역은 전화 접속 회의 액세스 번호를 해당 다이얼 플랜과 연결합니다. 다이얼 플랜을 설정할 때 해당 다이얼 플랜에 적용할 전화 접속 회의 지역을 지정할 수 있습니다. 그런 다음 전화 접속 액세스 번호를 만들 때 해당 액세스 번호를 적절한 다이얼 플랜과 연결하는 지역을 선택할 수 있습니다.

또한 다이얼 플랜을 만들 때 다이얼 플랜의 범위를 지정할 수 있습니다. 지정할 수 있는 범위는 사용자 범위, 풀 범위 또는 사이트 범위입니다. 모든 사용자에게는 해당 사용자에게 적용되는 가장 좁은 범위의 다이얼 플랜이 할당됩니다. 예를 들어 사용자 수준 다이얼 플랜이 적용되는 사용자에게는 사용자 수준 다이얼 플랜이 할당됩니다. 그러나 사용자 수준 다이얼 플랜이 적용되지 않는 사용자에게는 풀 수준 다이얼 플랜이 할당되고, 풀 수준 다이얼 플랜이 적용되지 않는 사용자에게는 사이트 수준 다이얼 플랜이 할당됩니다. 또한 사이트 수준 다이얼 플랜이 적용되지 않는 사용자에게는 전역 다이얼 플랜이 할당됩니다.

다이얼 플랜을 구성하기 전에 지역 이름 지정 및 사용 방법을 계획해야 합니다. 전화 접속 회의 지역에 대해 고려해야 할 사항은 다음과 같습니다.

  - 지역은 일반적으로 단일 사무실 또는 사무실 그룹과 연관된 지리적 영역입니다.

  - 언어는 전화 접속 액세스 번호와 연관됩니다. 여러 언어를 사용하는 지리적 영역을 지원하려면 여러 언어를 지원하도록 지역을 정의할 방법을 결정해야 합니다. 예를 들어 지리적 위치와 언어의 조합에 따라 여러 지역을 정의하거나, 지리적 위치에 따라 단일 지역을 정의하고 각 언어에 대해 서로 다른 전화 접속 액세스 번호를 지정할 수 있습니다.

  - 사용자가 모임을 예약하면 기본적으로 모임에서 해당 사용자의 다이얼 플랜에 지정된 지역을 사용합니다.

  - 기본적으로 해당 지역의 모든 전화 접속 액세스 번호가 모임 초대에 포함됩니다.

  - 지역을 명확히 인식할 수 있도록 이름을 지정하는 것이 중요합니다. 사용자는 지역 이름을 사용하여 다른 액세스 번호가 초대에 포함되도록 모임 지역을 변경할 수 있습니다. 사용자가 Outlook을 사용 하 여 모임을 예약할 때 사용자는 Lync 2013의 온라인 모임 추가 기능을 사용 하 여 지역을 변경 합니다.

  - 전화 접속을 통해 회의에 참가하려는 모든 초대 대상자가 전화 회의 초대에서 로컬 액세스 번호를 확인할 수 있도록 지역을 설계해야 합니다.

  - Lync Server 관리 셸 cmdlet을 사용 하 여 전화 접속 회의 설정 페이지에 있는 지역 내의 액세스 번호가 표시 되는 순서를 구성할 수 있습니다 (즉, 회의 초대에 표시 되는 순서).

  - 위치에 관계없이 모든 사용자는 표시된 모든 전화 접속 액세스 번호로 전화를 걸어 전화 회의에 참가할 수 있습니다.

</div>

<div>

## <a name="planning-for-conference-directories"></a>전화 회의 디렉터리 계획

전화 회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 회의 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 관리 합니다. 전화 접속 ID의 형식은 다음과 같습니다.

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

전화 회의 디렉터리를 여러 개 만들면 상당히 많은 수의 전화 회의가 만들어질 때까지 전화 회의 ID가 짧게 유지될 수 있습니다. 전화 회의 ID를 약 6자리로 유지하려면 사용자당 전화 회의 수가 보편적인 조직의 경우 풀의 사용자 999명당 하나의 전화 회의 디렉터리를 만드는 것이 좋습니다. 이 지침을 사용하면 대개 전화 회의 ID가 짧게 유지될 수 있습니다. 그러나 회의 디렉터리 수가 풀 전체에서 9개를 초과하면 추가 전화 회의를 지원하기 위해 회의 ID 번호가 길어집니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)  
[Lync Server 2013의 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

