---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 7c62ef5ec984fe89033aa4813bca9674979c1c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196944"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="5650e-103">비즈니스용 Skype 서버에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="5650e-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="5650e-105">회의 작업 부하와 선택한 전화 접속 회의를 포함 하는 토폴로지를 만든 후에는 추가 단계를 수행 하 여 전화 접속 회의를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="5650e-106">이 항목을 읽기 전에 비즈니스용 [Skype 서버에서 전화 접속 회의에 대 한 요금제](../../plan-your-deployment/conferencing/dial-in-conferencing.md), 비즈니스용 [skype 서버의 회의에 대 한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), [배포 순서도 및 검사 목록에 대 한 자세한 내용을 확인 하세요. 전화 접속 회의](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="5650e-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="5650e-107">전화 접속 회의를 구성 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="5650e-108">다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="5650e-109">전화 접속 회의 영역 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="5650e-110">전화 접속 액세스 번호 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="5650e-111">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="5650e-112">사용자 계정에 줄 URI 지정</span><span class="sxs-lookup"><span data-stu-id="5650e-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="5650e-113">또한 다음 선택적 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="5650e-114">이러한 선택적 작업에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 전화 접속 회의 관리](../../manage/conferencing/dial-in-conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="5650e-115">전화 접속 회의를 위한 PIN 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5650e-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="5650e-116">DTMF 명령에 대 한 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="5650e-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="5650e-117">회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="5650e-117">Create conference directories</span></span>
    
- <span data-ttu-id="5650e-118">컨퍼런스 참가 관리 및 공지 남기기</span><span class="sxs-lookup"><span data-stu-id="5650e-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="5650e-119">전화 접속 회의 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="5650e-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="5650e-120">전화 접속 사용자에 게 환영 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="5650e-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="5650e-121">다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-121">Configure dial plans</span></span>
<span data-ttu-id="5650e-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="5650e-122"></span></span>

<span data-ttu-id="5650e-123">전화 접속 회의를 배포 하는 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 또는 그 이상의 다이얼 플랜을 만들거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="5650e-124">또한 각 다이얼 플랜에는 E-164 형식의 완전 한 전화 번호로 변환 하는 규칙 인 정규화 규칙이 하나 이상 포함 되어 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="5650e-125">전화 접속 회의 사용자는 개인 id 번호 (PIN)와 전화 번호를 입력 하 여 인증 된 엔터프라이즈 사용자로 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="5650e-126">내선 번호를 완전 한 전화 번호로 변환 하 여 사용자가 전화 내선 번호만 입력 하는 경우 인증 받을 수 있는 정규화 규칙이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="5650e-127">전화 접속 회의에 대 한 다이얼 플랜을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="5650e-128">엔터프라이즈 음성을 배포할지 여부에 관계 없이 전화 접속 회의 영역을 추가 하도록 전역 다이얼 플랜을 수정 하 고 정규화 규칙이 전화 접속 액세스 번호를 정확 하 게 변환 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="5650e-129">자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="5650e-130">엔터프라이즈 음성을 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="5650e-131">전화 접속 회의 지역을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="5650e-132">자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="5650e-133">엔터프라이즈 음성을 배포한 경우 전화 접속 액세스 번호에 대 한 영역을 포함 하 고 적절 한 정규화 규칙을 사용 하도록 필요한 경우 Enterprise Voice dial 계획을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="5650e-134">전화 접속 액세스 번호에만 사용 되는 전용 다이얼 플랜을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="5650e-135">자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="5650e-136">정규화 규칙을 만드는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/normalization-rules.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="5650e-137">전화 접속 회의 영역 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="5650e-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="5650e-138"></span></span>

<span data-ttu-id="5650e-139">다이얼 플랜을 설정할 때 해당 다이얼 플랜에 적용 되는 전화 접속 회의 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="5650e-140">전화 접속 회의 영역은 전화 접속 회의 액세스 번호를 적절 한 다이얼 플랜에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="5650e-141">전화 접속 액세스 번호를 만들 때 적절 한 다이얼 플랜에 액세스 번호를 연결 하는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="5650e-142">모든 다이얼 플랜에 대 한 영역을 지정 하는 것이 중요 하기 때문에 모든 다이얼 플랜에 회의 영역이 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="5650e-143">지역이 모든 전화 접속 회의 다이얼 플랜에 설정 되어 있는지 여부를 확인 하려면 **Get-CsDialPlan 플랜** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="5650e-144">다이얼 플랜에서 지역이 누락 된 경우 **set-csdialplan** cmdlet을 사용 하 여 지역을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="5650e-145">또한 비즈니스용 Skype Server 제어판을 사용 하 여 기존 다이얼 플랜의 지역을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="5650e-146">비즈니스용 Skype Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="5650e-147">다이얼 플랜에 region 속성이 설정 되어 있는지 확인 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="5650e-148">RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="5650e-149">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5650e-150">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="5650e-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="5650e-152">이 예제에서는 조직에 대해 구성 된 모든 다이얼 플랜이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="5650e-153">반환 된 다이얼 플랜을 검토 하 여 전화 접속 회의 영역이 없는 것을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="5650e-154">자세한 내용은 [가져오기-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="5650e-155">다이얼 플랜의 region 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5650e-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="5650e-156">RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="5650e-157">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5650e-158">전화 접속 회의 영역이 없는 다이얼 플랜의 경우 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="5650e-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="5650e-160">이 예제에서는 DialinConferencingRegion 속성을 "US 서 부 해안"로 설정 하도록 Redmond Id가 포함 된 다이얼 플랜을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="5650e-161">자세한 내용은 [CsDialPlan 플랜 설정을](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="5650e-162">전화 접속 액세스 번호 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="5650e-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="5650e-163"></span></span>

<span data-ttu-id="5650e-164">전화 접속 회의를 배포 하는 경우 오디오 회의에 참가 하기 위해 사용자가 PSTN (공개 전환 전화 네트워크)에서 전화를 걸 수 있는 전화 번호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="5650e-165">이러한 전화 접속 액세스 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="5650e-166">전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 영역을 계획 한 다음 해당 지역으로 다이얼 플랜을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="5650e-167">지역에 대 한 자세한 내용은 [비즈니스용 Skype 서버의 전화 접속 회의 계획](../../plan-your-deployment/conferencing/dial-in-conferencing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="5650e-168">전화 접속 회의에 대 한 다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5650e-169">해당 액세스 번호의 AD DS (Active Directory 도메인 서비스) 복제가 완료 될 때까지 새 전화 접속 액세스 번호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="5650e-170">복제를 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5650e-171">전화 접속 액세스 번호를 만든 후에는 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 Active Directory 연락처 개체의 표시 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="5650e-172">표시 이름을 수정 하려면 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="5650e-173">Active Directory 개체를 수동으로 수정 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="5650e-174">전화 접속 액세스 번호를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5650e-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="5650e-175">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5650e-176">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5650e-177">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="5650e-178">**전화 접속 액세스 번호** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="5650e-179">**새로 만들기** 를 클릭 하 여 **새 전화 접속 액세스 번호**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="5650e-180">목록에서 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5650e-181">검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상한 결과가 생성 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="5650e-182">대신 원하는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="5650e-183">**표시 번호**에 공개 전환 전화 네트워크 (PSTN) 전화 사용자가 전화를 걸고 있는 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="5650e-184">이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="5650e-185">**표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="5650e-186">비즈니스용 Skype 검색 결과에서 전화 접속 액세스 번호와 연결 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="5650e-187">이 이름은 사용자가 액세스 번호를 호출할 때 클라이언트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="5650e-188">**줄 uri**에서 번호 앞에 + 기호를 포함 하 고 공백을 제외 하 고 TEL uri 형식의 전화 접속 액세스 번호에 대 한 E 자의 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="5650e-189">예를 들어, tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="5650e-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5650e-190">같은 회선 URI를 다른 전화 접속 회의 액세스 번호로 재사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="5650e-191">**SIP URI**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="5650e-192">입력란에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="5650e-193">이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 포함 하 여 다양 한 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5650e-194">같은 SIP URI를 다른 전화 접속 회의 액세스 번호에서 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="5650e-195">액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="5650e-196">SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="5650e-197">드롭다운 목록 상자에서이 전화 접속 액세스 번호를 지 원하는 회의 수행자 응용 프로그램의 도메인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="5650e-198">**풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5650e-199">액세스 번호를 만든 후에 풀을 변경 해야 하는 경우 [-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="5650e-200">**기본 언어**에서이 전화 접속 액세스 번호에 대 한 메시지가 재생 되는 언어를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="5650e-201">기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="5650e-202">지원 되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호 옆에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="5650e-203">) **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 호출자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="5650e-204">각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="5650e-205">사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="5650e-206">전화 접속 액세스 번호에 대 한 영역을 추가 하려면 **연결 된 지역**에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜에 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="5650e-207">전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="5650e-208">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="5650e-209">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5650e-209">Configure conferencing policies</span></span>
<span data-ttu-id="5650e-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="5650e-210"></span></span>

<span data-ttu-id="5650e-211">회의 정책은 참가자의 회의 환경을 지정 하는 사용자 계정 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-211">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="5650e-212">사이트 범위 또는 사용자 범위를 사용 하 여 회의 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-212">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="5650e-213">회의 정책 설정에는 회의 예약 및 참여의 여러 측면이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-213">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="5650e-214">여러 회의 정책 설정이 참가자에 대 한 전화 접속 회의를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-214">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="5650e-215">전화 접속 회의를 구성 하는 경우 이러한 필드가 조직에 맞게 적절 하 게 설정 되어 있는지 확인 하 고 필요에 따라 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-215">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="5650e-216">회의 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 정책 관리](../../manage/conferencing/conferencing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="5650e-217">사용자 계정에 줄 URI 지정</span><span class="sxs-lookup"><span data-stu-id="5650e-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="5650e-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="5650e-218"></span></span>

<span data-ttu-id="5650e-219">전화 접속 사용자는 전화 번호나 내선 번호와 PIN을 입력 하 여 인증 된 사용자로 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="5650e-220">비즈니스용 Skype 서버 사용자 계정에 지정 된 전화 통신 **회선 URI** 가 인증에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="5650e-221">이 항목의 절차에서는 단일 사용자 계정에 대 한 **회선 URI** 를 할당 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="5650e-222">여러 사용자 계정에 대 한 **줄 URI** 를 할당 해야 하는 경우 **Set csuser** cmdlet을 사용 하는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="5650e-223">샘플 스크립트를 사용 하 여 여러 사용자 계정에 **줄 uri** 를 할당 하는 방법에 대 한 자세한 내용은 [여러 사용자에 게 줄 uri 할당](https://go.microsoft.com/fwlink/p/?linkId=196945)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5650e-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="5650e-224">RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-useradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="5650e-225">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5650e-226">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="5650e-227">검색 필드에 전화 접속 회의에 대해 구성할 사용자의 이름을 입력 하거나, **필터 추가** 를 클릭 하 여 검색 필드를 지정 하 고 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="5650e-228">사용자 이름을 두 번 클릭 하 여 비즈니스용 **Skype 서버 사용자 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="5650e-229">**전화 통신**아래의 **줄 URI** 필드에 고유한 정규화 된 전화 번호 (예: tel: + 14255550200)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5650e-230">**전화 통신이** **pc 대 pc 전용**, **엔터프라이즈 음성**, **원격 통화 제어** 또는 **원격 통화 제어 전용 으로만**설정 된 경우에만 **줄 URI** 를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="5650e-231">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5650e-231">Click **Commit**.</span></span>
    

