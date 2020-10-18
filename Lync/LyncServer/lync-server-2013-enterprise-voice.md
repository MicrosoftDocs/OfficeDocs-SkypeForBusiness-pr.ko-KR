---
title: Lync Server 2013 Enterprise Voice
description: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11f2497cf99319317a75b81f02ed0d8ca797fbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574234"
---
# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-04-08_

Enterprise Voice를 사용 하는 경우 Lync Server에서는 기존 PBX (private branch exchange) 시스템을 향상 시키거나 교체 하기 위한 VoIP (독립 실행형 Voice over Internet Protocol)를 제공 합니다. Enterprise Voice 사용자는 조직의 VoIP 네트워크 또는 PBX에서 동료에 게 전화를 걸 수 있으며 조직 외부의 일반 전화 번호로 전화를 걸 수 있습니다. Enterprise Voice solution에는 answer, forward, transfer, 보류, divert, 릴리스 및 대기 및 향상 된 9-1-1 (E9-1-1) 통화와 같은 일반적인 통화 기능이 포함 되어 있습니다 (E9-1,-1은 미국 에서만 사용 가능). 또한 Enterprise Voice에서는 다양 한 범위의 현재 및 오래 된 IP 및 USB 장치를 지원 합니다.

<div>

## <a name="placing-and-receiving-calls"></a>전화 걸기 및 받기

Lync를 사용 하면 사용자가 키보드에 이름 또는 전화 번호를 입력 하거나 화면에 표시 되는 다이얼 패드를 사용 하 여 전화를 걸 수 있습니다. 사용자는 또한 대화 상대 목록에서 직접 통화를 시작할 수도 있습니다. Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 배포할 수도 있습니다.

사용자는 Lync Server에 등록 된 여러 전화 장치를 사용할 수 있으며,이를 쉽게 전환할 수 있습니다.

사용자는 IP 전화 장치의 사용자 지정 가능한 벨 소리와 PC의 메신저와 유사한 알림을 통해 모든 장치에 걸려오는 전화에 대한 알림을 동시에 수신합니다.

사용자는 또한 일반 전화기, PC 및 휴대폰에 연결되는 단일 전화 번호를 설정하여 어디에 있든지 전화를 받을 수 있습니다.

</div>

<div>

## <a name="basic-call-features"></a>기본 통화 기능

사용자는 통화 중일 때 또 다른 수신 전화에 응답하거나 발신 통화를 시작할 수 있으며 기존의 활성 통화는 자동으로 대기합니다. 직접 또는 첫 번째 사용자가 개인적으로 두 번째 사용자에게 말한 후 다른 사용자에게 통화를 전송할 수 있습니다. 사용자는 또한 다른 장치에 통화를 전송할 수도 있습니다. 예를 들어 사무실을 나오면서 활성 통화를 휴대폰으로 전송할 수 있습니다.

</div>

<div>

## <a name="richer-communications"></a>더욱 풍부한 커뮤니케이션

Lync를 사용 하 여 다른 사용자와 대화할 때 사용자는 통화에 텍스트, 비디오 또는 데스크톱 공유를 쉽게 추가할 수 있습니다. [방해 금지] 기능은 Lync의 현재 상태 설정에 통합 됩니다.

Exchange UM (통합 메시징)을 사용 하 여 Lync 및 Lync Server와 microsoft Exchange Server 2013 및 Microsoft Outlook 2013을 통합 합니다. 사용자는 Lync 창 및 전자 메일에 모두 새 음성 메일이 있는지 확인할 수 있습니다. 전자 메일의 경우 전자 메일 메시지에서 음성 메일 오디오를 클릭하여 재생하거나 음성 메일 메시지의 대화 내용을 볼 수 있습니다.

</div>

<div>

## <a name="advanced-calling-features"></a>고급 통화 기능

Enterprise Voice에는 Lync call 위임, 팀 호출, 그룹 통화 픽업 및 응답 그룹과 같은 몇 가지 고급 통화 기능도 포함 되어 있습니다.

Lync 호출 위임을 사용 하면 사용자가 **도구** \> **옵션** \> **착신 전환 설정**으로 이동 하 여 하나 이상의 도우미에 대 한 통화 처리를 위임할 수 있습니다. 대리인은 사용자를 대신해서 통화 차단, 전화 걸기 및 회의 시작을 포함한 여러 통화 작업을 수행할 수 있습니다.

<div>


> [!IMPORTANT]  
> 이와 유사한 다른 명명 된 기능인 Lync 일정 위임도 사용할 수 있습니다. Enterprise Voice 기능이 필요 하지 않으며 사용자가 Outlook에서 온라인 Lync 모임을 예약할 수 있습니다. 여기에서 해당 정보를 찾고 있다면 Exchange 위임 동기화를 사용 하도록 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">설정</A> 하는 방법에 대 한 정보를 확인 하는 것이 좋습니다.



</div>

팀 호출 기능을 사용 하면 팀의 모든 사용자가 통화에 응답할 수 있도록 받는 사람의 전화에 게 동시에 수신 전화를 연결 하도록 할 수 있습니다.

Lync Server 2013 년 2 2013 월에 대 한 누적 업데이트의 새로운 기능인 그룹 호출 Pickup에서는 사용자가 자신의 휴대폰에서 자신의 동료에 게 들어오는 호출에 응답할 수 있습니다. 그룹 통화 Pickup은 들어오는 전화가 의도 한 받는 사람의 휴대폰 에서만 울릴 수 있다는 점에서 팀 호출과는 다르며, 다른 모든 사용자는 통화 픽업 그룹 번호를 사용 하 여 전화를 걸어 응답 하도록 선택할 수도 있습니다.

통화를 지정된 에이전트에 대기시키고 지능적으로 라우팅하도록 응답 그룹을 설정할 수 있습니다. 일반적으로 IT 헬프데스크, 인사 부서 직통 전화 및 기타 내부 연락 센터에 사용됩니다.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Enterprise Voice 관리

Lync Server는 표준 및 게시 된 인터페이스를 사용 하 여 기존 인프라와 상호 작용 합니다. IP PBX 시스템 및 PSTN 네트워크에 대한 상호 연결에 게이트웨이 및 SIP 옵션(예: SIP 트렁크)을 지원하므로 중단을 최소화하면서 사용자를 천천히 Enterprise Voice로 마이그레이션할 수 있습니다. Lync Server는 전통적인 VoIP 솔루션과의 상호 운용성을 위해 g.711, 722 및 g.723.1와 같은 전통적인 코덱을 지원 합니다.

CAC (통화 허용 제어)를 사용 하는 경우 관리자는 제한 된 네트워크 링크에서 수행 되는 Lync Server 음성 및 비디오 트래픽 크기에 대 한 제한을 설정 하 고 새 통화가 제한을 초과 하는 경우 수행할 작업을 지정할 수 있습니다. 이러한 작업에는 대체 경로를 사용한 라우팅 또는 통화 거부가 포함될 수 있습니다.

Lync Server는 타사 Sba (survivable 분기 기기와 함께 작동 하 여 중앙 사이트에서 WAN 오류가 발생 하는 경우 지사에서 로컬 통화 서비스 및 PSTN에 대 한 연결을 제공 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

