---
title: 'Lync Server 2013: 분기 사용자에 대 한 VoIP 라우팅 정책 만들기'
description: 'Lync Server 2013: 분기 사용자에 대 한 VoIP 라우팅 정책을 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551084"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Lync Server 2013에서 분기 사용자에 대 한 VoIP 라우팅 정책 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-23_

분기 사이트의 사용자에 대해 별도의 VoIP(Voice Over IP) 정책을 만드는 것이 좋습니다. 이 정책에는 중앙 사이트의 게이트웨이에서 egress로 Sba (survivable Branch 기기 게이트웨이 또는 Sba (survivable 분기 서버 외부 게이트웨이와 백업 경로에서 egress에 대 한 경로가 포함 되어야 합니다. 사용자가 등록 되는 위치 (예: Sba (survivable Branch 어플라이언스 또는 Sba (survivable 분기 서버의 등록자 또는 중앙 사이트의 백업 등록자 클러스터에서)에 상관 없이 사용자의 VoIP 정책이 항상 적용 됩니다.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>분기 사용자에 대한 VoIP 라우팅 정책을 구성하려면

1.  사용자 수준 다이얼 플랜을 만들어 분기 사용자에게 할당합니다. (작업 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)

2.  사이트 사용자의 전화 거는 방식에 해당하는 정규화 규칙을 할당합니다. Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버 사용자가 중앙 사이트의 백업 등록자 풀로 장애 조치 (failover) 되 면 동일한 다이얼 플랜이 적용 됩니다. (작업 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)

3.  Sba (survivable Branch 기기 게이트웨이 또는 Sba (survivable Branch Server external gateway에서 egresses는 음성 경로를 구성 합니다. (작업 설명서에서 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md) 를 참조 하세요.)

4.  중앙 사이트에서 백업 등록자 풀 (중재 서버를 사용 하 여 배치 된)을 가리키도록 Sba (survivable Branch 기기 또는 Sba (survivable Branch Server 게이트웨이에서 백업 통화 경로를 설정 합니다. (Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server vendor 설명서를 참조 하세요.)
    
    <div>
    

    > [!NOTE]  
    > 이 백업 경로 설정을 사용 하면 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 사용할 수 없는 경우 분기 사용자에 대 한 인바운드 통화가 작동 하 게 됩니다 (예: 유지 관리를 위해 다운 된 경우). Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버의 등록자 및 중재 서버를 사용할 수 없고 사용자가 중앙 사이트에서 백업 등록자 풀에 등록 되어 있으면 인바운드 전화를 사용자에 게 라우팅할 수 있습니다.

    
    </div>

**다음 단계**: [Lync Server 2013에서 음성 메일 다시 라우팅 설정 구성](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

