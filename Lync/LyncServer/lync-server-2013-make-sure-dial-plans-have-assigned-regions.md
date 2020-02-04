---
title: 'Lync Server 2013: 다이얼 플랜에 할당된 지역이 있는지 확인'
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="a69e3-102">다이얼 플랜 설정 Lync 서버 2013에 지역이 지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a69e3-103">_**마지막으로 수정한 주제:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="a69e3-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="a69e3-104">전화 접속 회의에 사용 되는 다이얼 플랜에는 전화 접속 회의 액세스 번호를 적절 한 다이얼 플랜에 연결 하기 위한 **전화 접속 회의 영역이** 지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="a69e3-105">다이얼 플랜을 설정할 때 해당 다이얼 플랜에 적용 되는 전화 접속 회의 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="a69e3-106">그런 다음 전화 접속 액세스 번호를 만들 때 적절 한 다이얼 플랜에 액세스 번호를 연결 하는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="a69e3-107">모든 다이얼 플랜에 대 한 영역을 지정 하는 것이 중요 하기 때문에이 절차를 사용 하 여 모든 다이얼 플랜에 지역이 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="a69e3-108">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-108">This step is optional.</span></span>

<span data-ttu-id="a69e3-109">**Get-CsDialPlan 플랜** cmdlet을 사용 하 여 영역이 모든 전화 접속 회의 다이얼 플랜에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="a69e3-110">다이얼 플랜에서 지역이 누락 된 경우 **set-csdialplan** cmdlet을 사용 하 여 지역을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="a69e3-111">또한 Lync Server 제어판을 사용 하 여 기존 다이얼 플랜의 지역을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="a69e3-112">Lync Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a69e3-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="a69e3-113">다이얼 플랜에 region 속성이 설정 되어 있는지 확인 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="a69e3-114">RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="a69e3-115">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a69e3-116">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="a69e3-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="a69e3-118">이 예제에서는 조직에 대해 구성 된 모든 다이얼 플랜이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="a69e3-119">반환 된 다이얼 플랜을 검토 하 여 전화 접속 회의 영역이 없는 것을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="a69e3-120">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a69e3-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="a69e3-121">다이얼 플랜의 region 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a69e3-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="a69e3-122">RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="a69e3-123">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a69e3-124">전화 접속 회의 영역이 없는 다이얼 플랜의 경우 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="a69e3-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="a69e3-126">이 예제에서는 DialinConferencingRegion 속성을 "US 서 부 해안"로 설정 하도록 Redmond Id가 포함 된 다이얼 플랜을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e3-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="a69e3-127">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a69e3-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

