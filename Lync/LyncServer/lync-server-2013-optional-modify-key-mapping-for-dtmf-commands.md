---
title: 'Lync Server 2013: (선택 사항) DTMF 명령에 대 한 키 매핑 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a6d9d2cf2e97f7b04209d1ca8aab7bdc23456
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>반드시 Lync Server 2013의 DTMF 명령에 대 한 키 매핑 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-30_

전화 접속 회의 사용자는 전화기 키패드의 키를 눌러 DTMF(Dual-tone Multi-frequency) 명령을 수행할 수 있습니다. DTMF 명령을 사용하면 회의에 전화 접속한 사용자가 전화기의 키패드를 사용하여 음소거 설정 및 해제 또는 회의 잠금 설정 및 해제와 같은 회의 설정을 제어할 수 있습니다. cmdlet를 사용하여 DTMF 명령에 사용되는 키를 수정할 수 있습니다. 이 단계는 선택 사항입니다.

<div>


> [!NOTE]  
> 이러한 cmdlet 및 가능한 DTMF 옵션에 대 한 자세한 내용은 Lync Server Management Shell 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하십시오.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>DTMF 명령의 키 매핑을 수정하려면

1.  **RTCUniversalServerAdmins** 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        Get-CsDialinConferencingDtmfConfiguration
    
    이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 반환합니다.

4.  다음 cmdlet를 실행하고 변경할 각 옵션에 대해 누를 키를 지정합니다.
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 수정합니다.
    
    예를 들면 다음과 같습니다.
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    이 예에서는 알림을 사용하거나 사용하지 않도록 설정하기 위해 누르는 키와 모든 참가자에 대해 음소거를 설정 및 해제하기 위해 누르는 키를 바꿉니다. Identity가 지정되지 않았으므로 이 변경은 전역 DTMF 설정에 적용됩니다.

5.  (선택 사항) 특정 사이트에 대해 DTMF 명령 집합을 추가로 만들려면 사이트 ID와 함께 **New-CsDialinConferencingDtmfConfiguration** cmdlet를 사용합니다. 사이트에 대해 새 DTMF 설정을 만들면 이 사이트 설정이 전역 설정보다 우선합니다. 자세한 내용은 Lync Server 관리 셸 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

