---
title: 'Lync Server 2013: 음성 메일 다시 라우팅 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="5461a-102">Lync Server 2013에서 음성 메일 다시 라우팅 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5461a-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5461a-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5461a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5461a-104">중앙 사이트에 UM (통합 메시징)이 설치 되어 있고 Exchange UM 메시지 자동 전화 교환 (AA)이 배포 되는 경우 Survivable 분기 기기와 Survivable Branch 서버는 WAN을 중단 하는 동안 분기 사용자에 게 음성 메일 survivability을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="5461a-105">Exchange 관리자가 메시지를 수락 하도록 AA를 구성 하 여 사용자에 게 전송 하거나 교환원에 게 전송 하는 등의 다른 일반 기능을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="5461a-106">또는 일반 AA 또는 AA 사용자 지정을 사용 하 여 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="5461a-107">자세한 내용은 계획 설명서의 [Lync Server 2013의 지점 사이트 복원 요구 사항에 대](lync-server-2013-branch-site-resiliency-requirements.md) 한 "음성 메일 Survivability 준비" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5461a-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="5461a-108">음성 메일 survivability를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="5461a-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="5461a-109">Exchange 관리자에 게 메시지를 수락 하도록 AA를 구성 하도록 요청 (Exchange 셸에서는 다음 cmdlet을 사용 합니다. **Set-UMAutoAttendant 전화 교환 \<AA 이름\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="5461a-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="5461a-110">메시지를 남기기 (*SendVoiceMsgEnabled*) 할 수 있도록 지정 하는 매개 변수는 기본적으로 true입니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="5461a-111">Lync Server 관리 셸에서 **CSVoiceMailReroutingConfiguration** cmdlet을 사용 하 여 Survivable branch 기기 또는 Survivable branch 서버의 음성 메일 다시 라우팅 구성에서 Exchange UM 자동 전화 번호로 AA 전화 번호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5461a-112">나중에 음성 메일 다시 라우팅 설정을 수정 해야 하는 경우 <STRONG>CsVoiceMailReRoutingConfiguration</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="5461a-113">자세한 내용은 셸 도움말 항목의 <STRONG>New</STRONG> 및 <STRONG>Set CSVoiceMailReroutingConfiguration</STRONG>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5461a-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="5461a-114">분기 사용자의 Exchange UM 다이얼 플랜에 해당 하는 Exchange UM 구독자 액세스 번호를 Survivable Branch 기기 또는 Survivable Branch 서버의 음성 메일 다시 라우팅 구성에 있는 Exchange UM 구독자 액세스 번호로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5461a-115">WAN을 중단 하는 동안 음성 메일 가져오기 기능에 대 한 액세스 권한을 필요로 하는 모든 분기 사용자와 연결 되는 다이얼 플랜을 하나만 갖도록 Exchange UM 사용자의 다이얼 플랜을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="5461a-116">Survivable Branch 기기 또는 Survivable Branch 서버의 **다음 단계** : [Survivable branch 기기의 가정용 사용자 또는 Lync Server 2013의 서버](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5461a-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

