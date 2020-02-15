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
ms.openlocfilehash: f25ca766ab7292aeeba0d2e621eccff5a0c47fb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="7bcaf-102">다이얼 플랜 Lync Server 2013에 지역이 할당 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="7bcaf-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bcaf-103">_**마지막으로 수정 된 항목:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="7bcaf-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="7bcaf-p101">전화 접속 회의에 사용되는 다이얼 플랜에는 전화 접속 회의 액세스 번호를 적절한 다이얼 플랜에 연결하는 **전화 접속 회의 지역**이 지정되어 있어야 합니다. 다이얼 플랜을 설정할 때는 해당 다이얼 플랜에 적용되는 전화 접속 회의 지역을 지정합니다. 그런 다음 전화 접속 액세스 번호를 만들 때 액세스 번호를 적절한 다이얼 플랜에 연결하는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="7bcaf-p102">모든 다이얼 플랜에 대해 지역을 지정하는 것이 중요하므로, 다음 절차에 따라 모든 다이얼 플랜에 지역이 있는지 확인하는 것이 좋습니다. 이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="7bcaf-109">**Get-CsDialPlan** cmdlet을 사용하여 해당 지역이 모든 전화 접속 회의 다이얼 플랜에 대해 설정되어 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="7bcaf-110">해당 지역이 다이얼 플랜에서 누락된 경우 **Set-CsDialPlan** cmdlet을 사용하여 이 지역을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="7bcaf-111">Lync Server 제어판을 사용 하 여 기존 다이얼 플랜에서 지역을 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="7bcaf-112">Lync Server 제어판 사용에 대 한 자세한 내용은 [Lync server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="7bcaf-113">다이얼 플랜에 지역 속성 집합이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="7bcaf-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="7bcaf-114">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="7bcaf-115">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7bcaf-116">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="7bcaf-117">예:</span><span class="sxs-lookup"><span data-stu-id="7bcaf-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="7bcaf-118">이 예에서는 조직에 대해 구성된 모든 다이얼 플랜이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="7bcaf-119">반환된 다이얼 플랜을 검토하여 전화 접속 회의 지역이 누락된 항목이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="7bcaf-120">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="7bcaf-121">다이얼 플랜에 대해 지역 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7bcaf-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="7bcaf-122">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="7bcaf-123">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7bcaf-124">전화 접속 회의 지역이 누락된 다이얼 플랜에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="7bcaf-125">예:</span><span class="sxs-lookup"><span data-stu-id="7bcaf-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="7bcaf-126">이 예에서는 ID가 Redmond인 다이얼 플랜이 수정되어 DialinConferencingRegion 속성이 "US West Coast"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="7bcaf-127">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bcaf-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

