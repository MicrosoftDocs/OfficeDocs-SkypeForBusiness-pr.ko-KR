---
title: 'Lync Server 2013: 다이얼 플랜에 할당 된 지역이 있는지 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9f9a67a65b870edd75259bca7c74a1fae2749f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534565"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>다이얼 플랜 Lync Server 2013에 지역이 할당 되었는지 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2010-11-02_

전화 접속 회의에 사용되는 다이얼 플랜에는 전화 접속 회의 액세스 번호를 적절한 다이얼 플랜에 연결하는 **전화 접속 회의 지역**이 지정되어 있어야 합니다. 다이얼 플랜을 설정할 때는 해당 다이얼 플랜에 적용되는 전화 접속 회의 지역을 지정합니다. 그런 다음 전화 접속 액세스 번호를 만들 때 액세스 번호를 적절한 다이얼 플랜에 연결하는 지역을 선택합니다.

모든 다이얼 플랜에 대해 지역을 지정하는 것이 중요하므로, 다음 절차에 따라 모든 다이얼 플랜에 지역이 있는지 확인하는 것이 좋습니다. 이 단계는 선택 사항입니다.

**Get-CsDialPlan** cmdlet을 사용하여 해당 지역이 모든 전화 접속 회의 다이얼 플랜에 대해 설정되어 있는지 여부를 확인합니다. 해당 지역이 다이얼 플랜에서 누락된 경우 **Set-CsDialPlan** cmdlet을 사용하여 이 지역을 설정할 수 있습니다. Lync Server 제어판을 사용 하 여 기존 다이얼 플랜에서 지역을 업데이트할 수도 있습니다. Lync Server 제어판 사용에 대 한 자세한 내용은 [Lync server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오.

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>다이얼 플랜에 지역 속성 집합이 있는지 확인하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    예:
    
        Get-CsDialPlan
    
    이 예에서는 조직에 대해 구성된 모든 다이얼 플랜이 반환됩니다.

4.  반환된 다이얼 플랜을 검토하여 전화 접속 회의 지역이 누락된 항목이 있는지 확인합니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>다이얼 플랜에 대해 지역 속성을 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  전화 접속 회의 지역이 누락된 다이얼 플랜에 대해 다음을 실행합니다.
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    예:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    이 예에서는 ID가 Redmond인 다이얼 플랜이 수정되어 DialinConferencingRegion 속성이 "US West Coast"로 설정됩니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

