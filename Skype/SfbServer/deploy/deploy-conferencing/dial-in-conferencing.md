---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버에서 전화 접속 회의를 구성하는 방법을 배워야 합니다.'
ms.openlocfilehash: 92c282c87576e3d46353dabd8235521fe0097c11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820728"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="6ff87-103">비즈니스용 Skype 서버에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="6ff87-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="6ff87-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에서 전화 접속 회의를 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="6ff87-105">회의 작업 부하 및 선택된 전화 접속 회의를 포함하는 토폴로지가 만들어진 후 추가 단계를 수행하여 전화 접속 회의를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="6ff87-106">이 항목을 읽기 전에 비즈니스용 [Skype](../../plan-your-deployment/conferencing/dial-in-conferencing.md)서버의 전화 접속 회의 계획, 비즈니스용 [Skype](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항 및 전화 접속 회의에 대한 배포 흐름도 및 검사 목록을 읽어야 [합니다.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)</span><span class="sxs-lookup"><span data-stu-id="6ff87-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="6ff87-107">전화 접속 회의를 구성하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="6ff87-108">다이얼 플랜을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="6ff87-109">전화 접속 회의 지역 구성</span><span class="sxs-lookup"><span data-stu-id="6ff87-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="6ff87-110">전화 접속 액세스 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="6ff87-111">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="6ff87-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="6ff87-112">사용자 계정에 줄 URI 할당</span><span class="sxs-lookup"><span data-stu-id="6ff87-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="6ff87-113">또한 다음과 같은 선택적 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="6ff87-114">이러한 선택적 작업에 대한 자세한 내용은 비즈니스용 Skype 서버에서 전화 접속 회의 [관리를 참조하세요.](../../manage/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="6ff87-115">전화 접속 회의에 대한 PIN 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6ff87-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="6ff87-116">DTMF 명령에 대한 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="6ff87-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="6ff87-117">회의렉터 만들기</span><span class="sxs-lookup"><span data-stu-id="6ff87-117">Create conference directories</span></span>
    
- <span data-ttu-id="6ff87-118">회의 참가 및 나가기 공지 관리</span><span class="sxs-lookup"><span data-stu-id="6ff87-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="6ff87-119">전화 접속 회의 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="6ff87-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="6ff87-120">전화 접속 사용자에게 환영 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="6ff87-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="6ff87-121">다이얼 플랜을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-121">Configure dial plans</span></span>
<span data-ttu-id="6ff87-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="6ff87-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="6ff87-123">전화 접속 회의를 배포할 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만들거나 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="6ff87-124">또한 각 다이얼 플랜에 하나 이상의 정규화 규칙(내선 번호를 E.164 형식의 전체 전화 번호로 변환하는 규칙)이 포함되어 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="6ff87-125">전화 접속 회의의 사용자는 PIN(개인 식별 번호) 및 전화 번호를 입력하여 인증된 엔터프라이즈 사용자로 전화 회의에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="6ff87-126">사용자들이 전화 내선 번호를 입력할 때 사용자를 인증할 수 있도록 내선 번호를 완전한 전화 번호로 변환하는 정규화 규칙이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="6ff87-127">전화 접속 회의에 대한 다이얼 플랜을 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6ff87-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="6ff87-128">배포 여부에 Enterprise Voice 전역 다이얼 플랜을 수정하여 전화 접속 회의 지역을 추가하고 정규화 규칙이 전화 접속 액세스 번호를 정확하게 변환하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="6ff87-129">자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 [만들기 또는 수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="6ff87-130">사용자 계정을 배포하지 Enterprise Voice 전화 접속 회의 액세스 번호에 대한 다이얼 플랜을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="6ff87-131">이 경우 전화 접속 회의 지역을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="6ff87-132">자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 [만들기 또는 수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="6ff87-133">배포한 Enterprise Voice 지역을 포함하도록 Enterprise Voice 다이얼 플랜을 수정하고 전화 접속 액세스 번호에 적절한 정규화 규칙을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ff87-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="6ff87-134">전화 접속 액세스 번호에만 사용되는 전용 다이얼 플랜을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="6ff87-135">자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 [만들기 또는 수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="6ff87-136">정규화 규칙을 만드는 데 대한 자세한 내용은 비즈니스용 Skype에서 정규화 규칙 만들기 또는 [수정을 참조하세요.](../../deploy/deploy-enterprise-voice/normalization-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="6ff87-137">전화 접속 회의 지역 구성</span><span class="sxs-lookup"><span data-stu-id="6ff87-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="6ff87-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="6ff87-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="6ff87-139">다이얼 플랜을 설정할 때는 해당 다이얼 플랜에 적용되는 전화 접속 회의 지역을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="6ff87-140">전화 접속 회의 지역은 전화 접속 회의 액세스 번호를 적절한 다이얼 플랜과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="6ff87-141">그런 다음 전화 접속 액세스 번호를 만들 때 해당 액세스 번호를 적절한 다이얼 플랜과 연결하는 지역을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="6ff87-142">모든 다이얼 플랜의 지역을 지정하는 것이 중요하기 때문에 모든 다이얼 플랜에 회의 지역이 있는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="6ff87-143">지역이 모든 전화 접속 회의 다이얼 플랜에 대해 설정되어 있는지 확인하기 위해 **Get-CsDialPlan** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="6ff87-144">해당 지역이 다이얼 플랜에서 누락된 경우 **Set-CsDialPlan** cmdlet을 사용하여 이 지역을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="6ff87-145">비즈니스용 Skype 서버 제어판을 사용하여 기존 다이얼 플랜의 지역을 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="6ff87-146">비즈니스용 Skype 서버 제어판 사용에 대한 자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 [수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="6ff87-147">다이얼 플랜에 지역 속성 집합이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="6ff87-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="6ff87-148">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="6ff87-149">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6ff87-150">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="6ff87-151">예:</span><span class="sxs-lookup"><span data-stu-id="6ff87-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="6ff87-152">이 예에서는 조직에 대해 구성된 모든 다이얼 플랜이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="6ff87-153">반환된 다이얼 플랜을 검토하여 전화 접속 회의 지역이 누락된 항목이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="6ff87-154">자세한 내용은 [Get-CsDialPlan을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6ff87-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="6ff87-155">다이얼 플랜에 대해 지역 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6ff87-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="6ff87-156">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="6ff87-157">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6ff87-158">전화 접속 회의 지역이 누락된 다이얼 플랜에 대해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="6ff87-159">예:</span><span class="sxs-lookup"><span data-stu-id="6ff87-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="6ff87-160">이 예에서는 ID가 Redmond인 다이얼 플랜이 수정되어 DialinConferencingRegion 속성이 "US West Coast"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="6ff87-161">자세한 내용은 [Set-CsDialPlan을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6ff87-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="6ff87-162">전화 접속 액세스 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="6ff87-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="6ff87-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="6ff87-p110">전화 접속 회의를 배포하려면 회의의 오디오 부분에 참가하기 위해 사용자가 PSTN(공중 전화망)을 통해 전화를 걸 수 있는 전화 번호를 설정해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대장 및 전화 접속 회의 설정 웹 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="6ff87-166">전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 지역을 계획한 다음 해당 지역이 포함된 다이얼 플랜을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="6ff87-167">지역에 대한 자세한 내용은 비즈니스용 Skype 서버의 전화 접속 회의 [계획을 참조하세요.](../../plan-your-deployment/conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="6ff87-168">전화 접속 회의에 대한 다이얼 플랜을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 [수정을 참조하세요.](../../deploy/deploy-enterprise-voice/dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ff87-169">해당 액세스 번호에 대해 AD DS(Active Directory 도메인 서비스) 복제가 완료되어야 새 전화 접속 액세스 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="6ff87-170">복제 작업은 몇 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ff87-171">전화 접속 액세스 번호를 만든 후 사용자가 올바른 액세스 번호를 보다 쉽게 식별할 수 있도록 Active Directory 대화 상대 개체에 대한 표시 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="6ff87-172">표시 이름을 수정하려면 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6ff87-173">Active Directory 개체는 수동으로 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="6ff87-174">전화 접속 액세스 번호를 만들 경우</span><span class="sxs-lookup"><span data-stu-id="6ff87-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="6ff87-175">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6ff87-176">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6ff87-177">왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="6ff87-178">전화 접속 **액세스** 번호 페이지에서 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="6ff87-179">**새로하기를** 클릭하여 새 전화 접속 액세스 **번호를 열 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="6ff87-180">목록에서 전화 접속 액세스 번호 중 하나를 클릭하고 편집을 **클릭한** 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6ff87-181">검색 필드를 사용하여 전화 접속 액세스 번호 목록에서 열의 내용을 검색하면 예상한 결과가 산출되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="6ff87-182">대신 원하는 열별로 목록을 정렬하여 보거나 변경할 전화 접속 액세스 번호를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="6ff87-183">표시 **번호에** PSTN(Public Switched Telephone Network) 전화 사용자가 전화 회의에 참가하기 위해 전화를 걸 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="6ff87-184">이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="6ff87-185">표시 **이름에** 전화 접속 액세스 번호에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="6ff87-186">이 이름은 비즈니스용 Skype 검색 결과의 전화 접속 액세스 번호와 연결된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="6ff87-187">이 이름은 사용자가 액세스 번호로 전화를 걸면 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="6ff87-188">줄 **URI에서** 번호 앞의 + 기호와 공백 제외를 포함하여 전화 접속 액세스 번호의 E.164 번호를 TEL URI 형식으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="6ff87-189">예: tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="6ff87-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6ff87-190">다른 전화 접속 회의 액세스 번호에서 동일한 줄 URI를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="6ff87-191">**SIP URI에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="6ff87-192">텍스트 상자에 이 전화 접속 회의 액세스 번호에 대한 고유한 SIP URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="6ff87-193">이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 비롯한 다양한 위치에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6ff87-194">다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="6ff87-195">액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="6ff87-196">SIP URI를 변경하는 유일한 방법은 액세스 번호를 삭제하고 다시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="6ff87-197">드롭다운 목록 상자에서 이 전화 접속 액세스 번호를 지원하는 회의 전화 접속 응용 프로그램의 도메인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="6ff87-198">**풀에서** 이 전화 접속 액세스 번호를 지원하는 회의 전화 접속 전화 접속 인스턴스를 실행하는 풀을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6ff87-199">액세스 번호를 만든 후 풀을 변경해야 하는 경우 [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet을 사용하거나 액세스 번호를 삭제하고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="6ff87-200">기본 **언어에서** 이 전화 접속 액세스 번호에 대한 프롬프트가 재생되는 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="6ff87-201">기본 언어는 회의 전화 회의에서 통화에 응답하는 데 사용하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="6ff87-202">지원되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="6ff87-203">(선택 사항) 보조 언어(최대 4개)에서 **추가를** 클릭하고 이 전화 접속 액세스 번호에 대한 발신자에 대해 지원할 추가 언어를 하나 이상 선택한 다음 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="6ff87-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="6ff87-204">각 전화 접속 액세스 번호에 대해 최대 4개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="6ff87-205">사용자는 전화 회의에 전화 접속할 때 전화 회의 ID를 입력하기 전에 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="6ff87-206">전화 접속 액세스 번호에 대한 지역을 추가하려면 연결된 지역 아래에서 **추가를** 클릭하고 이 전화 접속 액세스 번호의 다이얼 플랜과 연결된 지역을 하나 이상 클릭한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="6ff87-207">전화 접속 액세스 번호에서 지역을 삭제하려면 연결된 지역 아래에서 삭제할 지역을 클릭한 다음 제거를 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="6ff87-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="6ff87-208">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="6ff87-209">회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="6ff87-209">Configure conferencing policies</span></span>
<span data-ttu-id="6ff87-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="6ff87-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="6ff87-p122">회의 정책은 참가자의 회의 환경을 지정하는 사용자 계정 설정이며, 사이트 범위나 사용자 범위에서 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참가와 관련된 여러 측면이 포함됩니다. 여러 회의 정책 설정에서는 참가자를 위한 전화 접속 회의가 지원됩니다. 전화 접속 회의를 구성할 경우 이 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 필드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="6ff87-216">회의 정책 구성에 대한 자세한 내용은 비즈니스용 Skype 서버에서 회의 정책 [관리를 참조하세요.](../../manage/conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6ff87-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="6ff87-217">사용자 계정에 줄 URI 할당</span><span class="sxs-lookup"><span data-stu-id="6ff87-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="6ff87-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="6ff87-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="6ff87-219">전화 접속 사용자는 전화 번호 또는 내선 번호와 PIN을 입력하여 인증된 사용자로 전화 회의에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="6ff87-220">인증을 위해 비즈니스용 Skype 서버 사용자 계정에 지정된 전화 통신 줄 **URI가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="6ff87-221">이 항목의 절차에서는 단일 사용자 계정에 대해 **줄 URI** 를 할당하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="6ff87-222">여러 사용자 계정에 대해 **줄 URI** 를 할당해야 하는 경우 **Set-CsUser** cmdlet이 사용되는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="6ff87-223">예제 스크립트를 사용하여 여러 사용자 계정에 줄 **URI를** 할당하는 자세한 내용은 여러 사용자에게 줄 [URI 할당을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=196945)</span><span class="sxs-lookup"><span data-stu-id="6ff87-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="6ff87-224">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-UserAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="6ff87-225">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6ff87-226">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6ff87-227">검색 필드에 전화 접속 회의에 대해 구성할 사용자 이름을 입력하거나 **필터 추가** 를 클릭하여 검색 필드를 지정한 다음 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="6ff87-228">사용자 이름을 두 번 클릭하여 비즈니스용 **Skype** 서버 사용자 편집 대화 상자를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="6ff87-229">**전화 통신** 의 **줄 URI** 필드에 정규화된 고유한 전화 번호를 입력합니다(예: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="6ff87-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6ff87-230">전화 통신이 PC 대  **PC** 전용, Enterprise Voice, 원격 통화 제어 **또는** 원격  통화 제어로 설정된 경우만 줄 **URI를** 지정할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6ff87-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="6ff87-231">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff87-231">Click **Commit**.</span></span>
    

