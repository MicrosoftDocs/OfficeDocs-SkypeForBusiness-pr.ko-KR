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
ms.openlocfilehash: 9f327bfc533b28313e4728b13c7a69d6c16bc034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Lync Server 2013에서 음성 메일 다시 라우팅 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

Sba (survivable Branch 기기 및 Sba (survivable 분기 서버는 WAN 중단 중에 분기 사용자에 게 음성 메일 지 속성를 제공할 수 있으며,이 경우 Exchange um (통합 메시징)이 중앙 사이트에 설치 되 고 Exchange UM 메시지 자동 전화 교환 (AA)이 배포 됩니다. Exchange 관리자가 메시지만 수락하도록 AA를 구성하여 사용자나 교환원에게로 전환하는 등의 다른 일반 기능은 사용하지 않도록 설정하는 것이 좋습니다. 또는 일반 AA를 사용하거나 통화를 라우팅하도록 사용자 지정된 AA를 사용할 수 있습니다.

자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항의](lync-server-2013-branch-site-resiliency-requirements.md) "음성 메일 지 속성 준비" 섹션을 참조 하십시오.

<div>

## <a name="to-configure-voice-mail-survivability"></a>음성 메일 지속 가능성을 구성하려면

1.  Exchange 관리자에 게 다음 cmdlet을 사용 하 여 exchange 셸에서 메시지만 수락 하도록 구성 합니다 ( **Set-UMAutoAttendant 전화 교환 \<AA 이름\> -CallSomeoneEnabled $false**). 메시지 남겨 두기를 허용하도록 지정하는 매개 변수(*SendVoiceMsgEnabled*)는 기본적으로 true입니다.

2.  Lync Server 관리 셸에서 **new-csvoicemailreroutingconfiguration** cmdlet을 사용 하 여 Sba (survivable branch 기기 또는 Sba (survivable 분기 서버의 음성 메일 다시 라우팅 구성에서 AA 전화 번호를 Exchange UM 자동 전화 교환 전화 번호로 설정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 나중에 음성 메일 다시 라우팅 설정을 수정해야 하는 경우 <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet을 사용하여 수정합니다. 자세한 내용은 Shell 도움말 항목의 <STRONG>New-</STRONG> 및 <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>을 참조하십시오.

    
    </div>

3.  분기 사용자의 Exchange UM 다이얼 플랜에 해당 하는 Exchange UM 구독자 액세스 번호를 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버의 음성 메일 다시 라우팅 구성에 있는 Exchange UM 구독자 액세스 번호로 설정 합니다.
    
    <div>
    

    > [!NOTE]  
    > WAN 중단 시 음성 메일 가져오기 기능에 액세스 해야 하는 모든 분기 사용자에 게 하나의 다이얼 플랜이 연결 되도록 Exchange UM 사용자의 다이얼 플랜을 구성 합니다.

    
    </div>

Sba (survivable 분기 어플라이언스 또는 Sba (survivable 분기 서버에 대 한 **다음 단계** : [sba (survivable Branch 기기 또는 Lync Server 2013의 서버에 대 한 홈 사용자](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

