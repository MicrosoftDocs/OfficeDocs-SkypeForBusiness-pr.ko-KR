---
title: 'Lync Server 2013: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에 사용자 두기'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013의 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에 사용자 두기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-10_

Survivable Branch 기기 또는 Survivable Branch 서버에서 사용자를 처리 하는 프로세스는 프런트 엔드 풀의 사용자를 대신 하는 과정과 유사 합니다. 중앙 사이트에서 Survivable Branch 기기 또는 Survivable Branch 서버 절차를 수행 합니다.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Survivable Branch 기기 또는 Survivable Branch 서버의 가정용 사용자

1.  사용자를 Survivable Branch Server 또는 Survivable Branch 서버로 이동 하기 전에 Lync Server 관리 셸을 열고 다음을 수행 합니다.
    
      - Cmdlet **테스트-CsPstnOutboundCall** 를 실행 하 여 Survivable Branch 서버가 실행 중인지, 그리고 PSTN (공개 통신 네트워크) 연결이 구성 되어 있는지 확인 합니다. PSTN 게이트웨이 속성을 수정 해야 하는 경우에는 cmdlet **집합-CsPstnGateway**를 사용 합니다.
    
      - Cmdlet **Get-CsVoicePolicy** 를 실행 하 여 Survivable Branch 서버에서 사용자가 해당 VoIP 라우팅 정책을가지고 있는지 확인 합니다. VoIP 정책을 수정 해야 하는 경우 cmdlet **CsVoicePolicy**를 사용 합니다.
    
      - Cmdlet **CsVoicemailReroutingConfiguration** 를 실행 하 여 음성 메일 다시 라우팅 설정이 구성 되어 있는지 확인 합니다. 음성 메일 다시 라우팅 설정을 수정 해야 하는 경우 cmdlet **CsVoicemailReroutingConfiguration**를 사용 합니다.

2.  Lync Server 관리 셸에서 cmdlet **이동 CsUser** 를 실행 하 여 홈 사용자를 이동 합니다.

<div>


> [!NOTE]  
> Lync Server 제어판을 사용 하 여 필수 구성 요소 및 가정 사용자를 확인할 수도 있습니다.



</div>

<div>


> [!NOTE]  
> Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[CsUser 이동](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

