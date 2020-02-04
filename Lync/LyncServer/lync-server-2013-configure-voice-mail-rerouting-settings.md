---
title: 'Lync Server 2013: 음성 메일 다시 라우팅 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4ea243e87490bcabd48c866cce525d6bbd17077
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Lync Server 2013에서 음성 메일 다시 라우팅 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

중앙 사이트에 UM (통합 메시징)이 설치 되어 있고 Exchange UM 메시지 자동 전화 교환 (AA)이 배포 되는 경우 Survivable 분기 기기와 Survivable Branch 서버는 WAN을 중단 하는 동안 분기 사용자에 게 음성 메일 survivability을 제공할 수 있습니다. Exchange 관리자가 메시지를 수락 하도록 AA를 구성 하 여 사용자에 게 전송 하거나 교환원에 게 전송 하는 등의 다른 일반 기능을 사용 하지 않는 것이 좋습니다. 또는 일반 AA 또는 AA 사용자 지정을 사용 하 여 통화를 라우팅할 수 있습니다.

자세한 내용은 계획 설명서의 [Lync Server 2013의 지점 사이트 복원 요구 사항에 대](lync-server-2013-branch-site-resiliency-requirements.md) 한 "음성 메일 Survivability 준비" 섹션을 참조 하세요.

<div>

## <a name="to-configure-voice-mail-survivability"></a>음성 메일 survivability를 구성 하려면

1.  Exchange 관리자에 게 메시지를 수락 하도록 AA를 구성 하도록 요청 (Exchange 셸에서는 다음 cmdlet을 사용 합니다. **Set-UMAutoAttendant 전화 교환 \<AA 이름\> -CallSomeoneEnabled $false**. 메시지를 남기기 (*SendVoiceMsgEnabled*) 할 수 있도록 지정 하는 매개 변수는 기본적으로 true입니다.

2.  Lync Server 관리 셸에서 **CSVoiceMailReroutingConfiguration** cmdlet을 사용 하 여 Survivable branch 기기 또는 Survivable branch 서버의 음성 메일 다시 라우팅 구성에서 Exchange UM 자동 전화 번호로 AA 전화 번호를 설정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 나중에 음성 메일 다시 라우팅 설정을 수정 해야 하는 경우 <STRONG>CsVoiceMailReRoutingConfiguration</STRONG> cmdlet을 사용 합니다. 자세한 내용은 셸 도움말 항목의 <STRONG>New</STRONG> 및 <STRONG>Set CSVoiceMailReroutingConfiguration</STRONG>을 참조 하세요.

    
    </div>

3.  분기 사용자의 Exchange UM 다이얼 플랜에 해당 하는 Exchange UM 구독자 액세스 번호를 Survivable Branch 기기 또는 Survivable Branch 서버의 음성 메일 다시 라우팅 구성에 있는 Exchange UM 구독자 액세스 번호로 설정 합니다.
    
    <div>
    

    > [!NOTE]  
    > WAN을 중단 하는 동안 음성 메일 가져오기 기능에 대 한 액세스 권한을 필요로 하는 모든 분기 사용자와 연결 되는 다이얼 플랜을 하나만 갖도록 Exchange UM 사용자의 다이얼 플랜을 구성 합니다.

    
    </div>

Survivable Branch 기기 또는 Survivable Branch 서버의 **다음 단계** : [Survivable branch 기기의 가정용 사용자 또는 Lync Server 2013의 서버](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

