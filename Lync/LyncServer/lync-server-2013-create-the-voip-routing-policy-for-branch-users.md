---
title: 'Lync Server 2013: 분기 사용자에 대 한 VoIP 라우팅 정책 만들기'
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
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="33338-102">Lync Server 2013에서 분기 사용자에 대 한 VoIP 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="33338-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33338-103">_**마지막으로 수정 된 항목:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="33338-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="33338-104">분기 사이트의 사용자에 대해 별도의 VoIP(Voice Over IP) 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33338-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="33338-105">이 정책에는 중앙 사이트의 게이트웨이에서 egress로 Sba (survivable Branch 기기 게이트웨이 또는 Sba (survivable 분기 서버 외부 게이트웨이와 백업 경로에서 egress에 대 한 경로가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33338-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="33338-106">사용자가 등록 되는 위치 (예: Sba (survivable Branch 어플라이언스 또는 Sba (survivable 분기 서버의 등록자 또는 중앙 사이트의 백업 등록자 클러스터에서)에 상관 없이 사용자의 VoIP 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33338-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="33338-107">분기 사용자에 대한 VoIP 라우팅 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="33338-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="33338-108">사용자 수준 다이얼 플랜을 만들어 분기 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="33338-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="33338-109">(작업 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="33338-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="33338-110">사이트 사용자의 전화 거는 방식에 해당하는 정규화 규칙을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="33338-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="33338-111">Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버 사용자가 중앙 사이트의 백업 등록자 풀로 장애 조치 (failover) 되 면 동일한 다이얼 플랜이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33338-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="33338-112">(작업 설명서의 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="33338-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="33338-113">Sba (survivable Branch 기기 게이트웨이 또는 Sba (survivable Branch Server external gateway에서 egresses는 음성 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="33338-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="33338-114">(작업 설명서에서 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md) 를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="33338-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="33338-115">중앙 사이트에서 백업 등록자 풀 (중재 서버를 사용 하 여 배치 된)을 가리키도록 Sba (survivable Branch 기기 또는 Sba (survivable Branch Server 게이트웨이에서 백업 통화 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33338-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="33338-116">(Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server vendor 설명서를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="33338-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33338-117">이 백업 경로 설정을 사용 하면 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 사용할 수 없는 경우 분기 사용자에 대 한 인바운드 통화가 작동 하 게 됩니다 (예: 유지 관리를 위해 다운 된 경우).</span><span class="sxs-lookup"><span data-stu-id="33338-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="33338-118">Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버의 등록자 및 중재 서버를 사용할 수 없고 사용자가 중앙 사이트에서 백업 등록자 풀에 등록 되어 있으면 인바운드 전화를 사용자에 게 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33338-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="33338-119">**다음 단계**: [Lync Server 2013에서 음성 메일 다시 라우팅 설정 구성](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="33338-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

