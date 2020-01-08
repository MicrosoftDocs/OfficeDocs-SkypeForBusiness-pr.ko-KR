---
title: 'Lync Server 2013: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에 사용자 두기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="e6cfa-102">Lync Server 2013의 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에 사용자 두기</span><span class="sxs-lookup"><span data-stu-id="e6cfa-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6cfa-103">_**마지막으로 수정한 주제:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="e6cfa-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="e6cfa-104">Survivable Branch 기기 또는 Survivable Branch 서버에서 사용자를 처리 하는 프로세스는 프런트 엔드 풀의 사용자를 대신 하는 과정과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="e6cfa-105">중앙 사이트에서 Survivable Branch 기기 또는 Survivable Branch 서버 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="e6cfa-106">Survivable Branch 기기 또는 Survivable Branch 서버의 가정용 사용자</span><span class="sxs-lookup"><span data-stu-id="e6cfa-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="e6cfa-107">사용자를 Survivable Branch Server 또는 Survivable Branch 서버로 이동 하기 전에 Lync Server 관리 셸을 열고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="e6cfa-108">Cmdlet **테스트-CsPstnOutboundCall** 를 실행 하 여 Survivable Branch 서버가 실행 중인지, 그리고 PSTN (공개 통신 네트워크) 연결이 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="e6cfa-109">PSTN 게이트웨이 속성을 수정 해야 하는 경우에는 cmdlet **집합-CsPstnGateway**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="e6cfa-110">Cmdlet **Get-CsVoicePolicy** 를 실행 하 여 Survivable Branch 서버에서 사용자가 해당 VoIP 라우팅 정책을가지고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="e6cfa-111">VoIP 정책을 수정 해야 하는 경우 cmdlet **CsVoicePolicy**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="e6cfa-112">Cmdlet **CsVoicemailReroutingConfiguration** 를 실행 하 여 음성 메일 다시 라우팅 설정이 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="e6cfa-113">음성 메일 다시 라우팅 설정을 수정 해야 하는 경우 cmdlet **CsVoicemailReroutingConfiguration**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="e6cfa-114">Lync Server 관리 셸에서 cmdlet **이동 CsUser** 를 실행 하 여 홈 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6cfa-115">Lync Server 제어판을 사용 하 여 필수 구성 요소 및 가정 사용자를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e6cfa-116">Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6cfa-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6cfa-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6cfa-117">See Also</span></span>


[<span data-ttu-id="e6cfa-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="e6cfa-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="e6cfa-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="e6cfa-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="e6cfa-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6cfa-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="e6cfa-121">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="e6cfa-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

