---
title: 'Lync Server 2013: 분기 사용자에 대한 VoIP 라우팅 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Lync Server 2013에서 분기 사용자에 대한 VoIP 라우팅 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-23_

지사 사이트의 사용자를 위해 별도의 VoIP (voice over IP) 정책을 만드는 것이 좋습니다. 이 정책에는 중앙 사이트의 게이트웨이에서 Survivable Branch 기기 게이트웨이 또는 Survivable Branch 서버 외부 게이트웨이 및 백업 경로에서 egress 까지의 경로가 포함 되어야 합니다. 사용자가 등록 되는 위치에 관계 없이, Survivable Branch 기기 또는 Survivable Branch 서버의 레지스트라 또는 중앙 사이트의 백업 등록자 클러스터에서 사용자의 VoIP 정책이 항상 적용 됩니다.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>지사 사용자를 위한 VoIP 라우팅 정책 구성

1.  사용자 수준 다이얼 플랜을 만들어 분기 사용자에 게 할당 합니다. (운영 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)

2.  해당 사이트의 사용자에 대 한 전화 걸기 습관에 해당 하는 정규화 규칙을 할당 합니다. Survivable Branch 기기 또는 Survivable Branch 서버 사용자가 중앙 사이트의 백업 등록자 풀로 장애 조치 되는 경우 동일한 다이얼 플랜이 적용 됩니다. (운영 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)

3.  Survivable Branch 기기 게이트웨이 또는 Survivable Branch Server 외부 게이트웨이에서 egresses 하는 음성 경로를 구성 합니다. (운영 설명서의 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md) 를 참조 하세요.)

4.  Survivable Branch 기기 또는 Survivable Branch 서버 게이트웨이에서 백업 통화 경로를 설정 하 여 중앙 사이트에서 백업 등록자 풀 (collocated를 사용 하는 서버)을 가리킵니다. (Survivable Branch 기기 또는 Survivable Branch Server 공급 업체 문서를 참조 하세요.)
    
    <div>
    

    > [!NOTE]  
    > 이 백업 경로 설정에서는 Survivable Branch 기기 또는 Survivable Branch 서버를 사용할 수 없는 경우, 예를 들어 유지 관리를 위해 지점 사용자에 게 들어오는 인바운드 통화가 작동 하는지 확인할 수 있습니다. Survivable Branch 기기 또는 Survivable Branch 서버의 등록자 및 조정 서버를 사용할 수 없고 사용자가 중앙 사이트의 백업 등록자 풀에 등록 되어 있는 경우에도 인바운드 통화를 사용자에 게 라우팅할 수 있습니다.

    
    </div>

**다음 단계**: [Lync Server 2013에서 음성 메일 다시 라우팅 설정을 구성](lync-server-2013-configure-voice-mail-rerouting-settings.md) 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

