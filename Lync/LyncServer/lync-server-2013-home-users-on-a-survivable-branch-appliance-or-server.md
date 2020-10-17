---
title: 'Lync Server 2013: Sba (survivable 분기 어플라이언스 또는 Server의 개인 사용자'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: add711ca547648a6071a22fee6a0bcd0eeb0f6c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528205"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013의 Sba (survivable 분기 어플라이언스 또는 서버에 있는 개인 사용자

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-10_

Sba (survivable 분기 어플라이언스 또는 Sba (survivable 분기 서버에서 사용자를 대신 하는 프로세스는 프런트 엔드 풀에서 사용자를 간 설정 하는 프로세스와 비슷합니다. 중앙 사이트에서 Sba (survivable Branch 기기 또는 Sba (survivable Branch Server 절차를 수행 합니다.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Survivable Branch Appliance 또는 지속 가능 분기 서버에 사용자를 두려면

1.  사용자를 Sba (survivable Branch Server 또는 Sba (survivable Branch 서버로 이동 하기 전에 Lync Server 관리 셸을 열고 다음 작업을 모두 수행 합니다.
    
      - Cmdlet **test-cspstnoutboundcall** 를 실행 하 여 Sba (survivable 분기 서버가 실행 중이 고 PSTN (공중 전화망) 연결이 구성 되어 있는지 확인 합니다. PSTN 게이트웨이 속성을 수정해야 할 경우 **Set-CsPstnGateway** cmdlet을 사용합니다.
    
      - Cmdlet Set-csvoicepolicy를 실행 하 여 Sba (survivable 분기 서버에서 **사용** 될 사용자에 게 적절 한 VoIP 라우팅 정책이 있는지 확인 합니다. VoIP 정책을 수정해야 할 경우 **Set-CsVoicePolicy** cmdlet을 사용합니다.
    
      - **Get-CsVoicemailReroutingConfiguration** cmdlet을 사용하여 음성 사서함 라우팅 설정이 구성되었는지 확인합니다. 음성 사서함 라우팅 설정을 수정해야 할 경우 **Set-CsVoicemailReroutingConfiguration** cmdlet을 사용합니다.

2.  Lync Server 관리 셸에서 cmdlet **이동 CsUser** 를 실행 하 여 홈 사용자를 이동 합니다.

<div>


> [!NOTE]  
> Lync Server 제어판을 사용 하 여 필수 구성 요소 및 가정 사용자를 확인할 수도 있습니다.



</div>

<div>


> [!NOTE]  
> Lync Server Sba (survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 대화방 카드를 볼 수 없습니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-cspstnoutboundcall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[New-csvoicemailreroutingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[CsUser 이동](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

