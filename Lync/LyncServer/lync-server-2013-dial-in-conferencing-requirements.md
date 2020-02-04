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
ms.openlocfilehash: 0c54e162aeda43730dea471732124023588e9041
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013의 전화 접속 회의 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

Lync Server 2013 배포 프로세스를 시작 하기 전에 다음을 계획 해야 합니다.

  - PSTN (공개 교환 전화 네트워크)에 연결 하는 데 사용할 구성

  - 전화 접속 로그인 회의 영역을 전화 접속 액세스 번호에 배정 하는 전략

  - 회의 디렉터리 만들기 전략

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>전화 접속 PSTN 연결 계획

전화 접속 회의에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이가 필요 합니다.

중앙 사이트 또는 지점 사이트에 중재 서버를 배포할 수 있습니다. 중앙 사이트에서는 프런트 엔드 풀 또는 스탠더드 버전 서버에서 중재 서버를 collocate 하거나 독립 실행형 서버 또는 풀에 배포할 수 있습니다. 지점 사이트에서는 독립 실행형 서버나 Survivable Branch 기기의 구성 요소로 중재 서버를 배포할 수 있습니다.

중앙 사이트 또는 지점 사이트에 PSTN 게이트웨이를 배포할 수 있습니다. 지점 사이트에서 PSTN 게이트웨이는 독립형 또는 Survivable Branch 기기의 구성 요소 일 수 있습니다.

<div>


> [!NOTE]  
> A/V 회의 서버는 미디어 바이패스를 지원 하지 않으므로 전화 접속 회의는 미디어 바이패스를 사용 하지 않습니다.



</div>

중재 서버 및 전화 접속 회의를 위한 PSTN 게이트웨이의 구성을 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버용 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하세요.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>전화 접속 회의 지역 계획

전화 접속 구성 중에 다이얼 플랜 및 전화 접속 회의 액세스 번호를 만듭니다. 다이얼 플랜은 전화 번호의 숫자와 패턴을 지정 하 고 전화 번호를 표준 전자 164 형식으로 변환 하는 정규화 규칙 집합으로, 통화 라우팅을 위한 것입니다. 전화 접속 회의 액세스 번호는 참가자가 전화 회의에 참가 하기 위해 전화를 거는 번호입니다.

모든 전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 되어 있어야 합니다. 전화 접속 회의 지역에서는 전화 접속 회의 액세스 번호와 다이얼 플랜을 연결 합니다. 다이얼 플랜을 설정할 때 다이얼 플랜에 적용 되는 전화 접속 회의 영역을 지정 합니다. 전화 접속 액세스 번호를 만들 때 적절 한 다이얼 플랜에 액세스 번호를 연결 하는 지역을 선택 합니다.

다이얼 플랜을 만들 때 사용자 범위, 풀 범위 또는 사이트 범위 등 다이얼 플랜의 범위를 지정 합니다. 모든 사용자는 사용자에 게 적용 되는 가장 좁은 범위에서 다이얼 플랜을 할당 받습니다. 예를 들어 사용자에 게 적용 되는 경우 사용자 수준 다이얼 플랜을 할당 받습니다. 사용자 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 풀 수준 다이얼 플랜을 할당 한 것입니다. 풀 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 사이트 수준 다이얼 플랜을 할당 한 것입니다. 사이트 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 전역 다이얼 플랜을 할당 합니다.

다이얼 플랜을 구성 하기 전에 지역을 이름 및 사용 하는 방법을 계획 하는 것이 중요 합니다. 전화 접속 회의 지역에는 다음 고려 사항이 적용 됩니다.

  - 영역은 일반적으로 office 또는 사무실 그룹과 연결 된 지리적 영역입니다.

  - 언어는 전화 접속 액세스 번호와 연결 됩니다. 여러 언어를 사용 하는 지리 영역을 지 원하는 경우 여러 언어를 지 원하는 지역을 정의 하는 방법을 결정 해야 합니다. 예를 들어 지역 및 언어의 조합에 따라 여러 지역을 정의 하거나, 지리를 기준으로 단일 지역을 정의 하 고 각 언어에 대 한 다른 전화 접속 액세스 번호를 사용할 수 있습니다.

  - 사용자가 모임을 예약 하면 기본적으로 해당 사용자의 다이얼 플랜에 지정 된 영역이 모임에 사용 됩니다.

  - 기본적으로 해당 지역의 모든 전화 접속 액세스 번호는 모임 초대에 포함 됩니다.

  - 분명 하 게 인식할 수 있도록 지역 이름을 구분 하는 것이 중요 합니다. 사용자는 다른 액세스 번호가 초대에 포함 되도록 지역 이름을 사용 하 여 모임 지역을 변경할 수 있습니다. 사용자가 Outlook을 사용 하 여 모임을 예약할 때 사용자는 Lync 2013의 온라인 모임 추가 기능을 사용 하 여 지역을 변경할 수 있습니다.

  - 전화를 걸고 싶어 하는 모든 초대 대 상자가 회의 초대에서 로컬 액세스 번호를 볼 수 있도록 지역을 디자인 해야 합니다.

  - Lync Server 관리 셸 cmdlet을 사용 하 여 전화 접속 회의 설정 페이지에 있는 지역 내의 액세스 번호가 표시 되는 순서를 구성할 수 있습니다 (즉, 회의 초대에 표시 되는 순서).

  - 모든 위치의 사용자는 전화 접속 액세스 번호를 호출 하 여 회의에 참가할 수 있습니다.

</div>

<div>

## <a name="planning-for-conference-directories"></a>컨퍼런스 디렉터리 계획

회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 모임 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 합니다. 전화 회의 ID의 형식은 다음과 같습니다.

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

여러 회의 디렉터리를 만들면 회의 Id가 매우 많은 회의를 만들 때까지 짧은 시간 동안 유지 되도록 할 수 있습니다. 사용자 당 일반적인 회의 수가 있는 조직에서 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만드는 것이 좋습니다. 이 지침을 사용 하 여 회의 Id를 일반적으로 작게 유지할 수 있습니다. 그러나, 풀 전체의 회의 디렉터리 수가 9 개를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 번호가 늘어납니다.

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

