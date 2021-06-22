---
title: 다이얼 플랜 만들기 및 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: 전화 걸기 Microsoft Teams 관리 센터 또는 Windows PowerShell(PSTN 통화 전화 걸기 전화 요금제)를 만들고 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046235"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="d36bf-103">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="d36bf-103">Create and manage dial plans</span></span>

<span data-ttu-id="d36bf-104">조직의 전화 걸기 계획을 계획하고 통화 라우팅을 위해 만들어야 하는 모든 정규화 규칙을 확인한 후 다이얼 계획을 만들 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="d36bf-105">유효한 라이선스가 있는 관리자 계정으로 Teams 관리 센터 또는 Microsoft Teams Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d36bf-106">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="d36bf-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="d36bf-107">다이얼 요금제 만들기</span><span class="sxs-lookup"><span data-stu-id="d36bf-107">Create a dial plan</span></span>

1. <span data-ttu-id="d36bf-108">관리 센터의 왼쪽 Microsoft Teams 음성 전화 걸기 계획으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="d36bf-109">추가 **를** 클릭한 다음 다이얼 요금제에 대한 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="d36bf-110">![다이얼 요금제 만들기를 위한 추가 페이지를 보여주는 스크린샷](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="d36bf-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="d36bf-111">전화 **걸기 계획 세부** 정보에서 사용자가 외부 줄을 얻기 위해 하나 이상의 앞자리(예: 9)에 전화를 걸 필요가 있는 경우 외부 전화 걸기 전단을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="d36bf-112">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="d36bf-112">To do this:</span></span>
    1. <span data-ttu-id="d36bf-113">외부 전화 **걸기** 연사 상자에 외부 전화 접속 도두사에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="d36bf-114">이 연결선은 최대 4자(#,\*, 0-9)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="d36bf-115">최적화된 **디바이스 전화 걸기를 켜기**</span><span class="sxs-lookup"><span data-stu-id="d36bf-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="d36bf-116">외부 전화 걸기 전신을 지정하는 경우 조직 외부에서 호출할 수 있도록 이 설정을 켜서 도우미를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="d36bf-117">정규화 **규칙에서** 다이얼 계획에 대해 하나 이상의 정규화 [규칙을](what-are-dial-plans.md#normalization-rules) 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="d36bf-118">각 다이얼 계획에는 하나 이상의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="d36bf-119">이렇게 하여 다음 중 하나 이상을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="d36bf-120">새 정규화 규칙을 만들고 다이얼 계획과 연결하려면 **추가를** 클릭한 다음 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="d36bf-121">다이얼 계획과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름의 왼쪽을 클릭하여 규칙을 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="d36bf-122">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="d36bf-123">다이얼 계획에서 정규화 규칙을 제거하려면 규칙 이름의 왼쪽을 클릭하여 규칙을 선택한 다음 **제거를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="d36bf-124">정규화 규칙을 원하는 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="d36bf-125">이동 **또는** **아래로 이동을** 클릭하여 목록의 규칙 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d36bf-126">Teams 위쪽에서 정규화 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d36bf-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d36bf-127">전화 걸기 번호가 두 개 이상의 정규화 규칙과 일치하도록 전화 걸기 계획을 설정한 경우 더 제한적인 규칙이 덜 제한적인 규칙보다 정렬되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="d36bf-128">"+"없이 전화 걸기 번호를 정규화하는 다이얼 플랜을 설정한 경우 호출 서비스는 테넌트 및 지역 전화 요금제 규칙을 사용하여 번호를 다시 정규화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="d36bf-129">두 번 정규화를 방지하기 위해 모든 정규화 규칙에서 숫자가 "+"로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="d36bf-130">직접 라우팅 고객은 [트렁크](direct-routing-translate-numbers.md) 번역 규칙을 사용하여 필요한 경우 "+"를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="d36bf-131">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-131">Click **Save**.</span></span>
7. <span data-ttu-id="d36bf-132">전화 걸기 계획을 테스트하려면 전화 걸기 계획에서 **전화** 번호를 입력한 다음 테스트 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="d36bf-133">다이얼 플랜 편집</span><span class="sxs-lookup"><span data-stu-id="d36bf-133">Edit a dial plan</span></span>

1. <span data-ttu-id="d36bf-134">관리 센터의 왼쪽 Microsoft Teams 음성 전화 걸기 계획으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="d36bf-135">다이얼 플랜 이름의 왼쪽을 클릭하여 다이얼 계획을 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d36bf-136">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d36bf-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="d36bf-137">사용자에게 전화 걸기 요금제 할당</span><span class="sxs-lookup"><span data-stu-id="d36bf-137">Assign a dial plan to users</span></span>

<span data-ttu-id="d36bf-138">정책을 할당하는 방식과 동일한 방식으로 다이얼 플랜을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="d36bf-139">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="d36bf-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="d36bf-140">PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="d36bf-140">Start PowerShell</span></span>
- <span data-ttu-id="d36bf-141">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="d36bf-142">다이얼 요금제 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="d36bf-142">Create and manage your dial plans</span></span>

<span data-ttu-id="d36bf-143">단일 cmdlet 또는 PowerShell 스크립트를 사용하여 테넌트 다이얼 계획을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="d36bf-144">단일 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="d36bf-144">Using single cmdlets</span></span>

- <span data-ttu-id="d36bf-145">새 다이얼 계획을 만들 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d36bf-146">다른 예제 및 매개 변수는 [New-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/new-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="d36bf-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="d36bf-147">기존 다이얼 플랜의 설정을 편집하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d36bf-148">다른 예제 및 매개 변수는 [Set-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/set-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="d36bf-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="d36bf-149">다이얼 플랜에 사용자를 추가하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="d36bf-150">다른 예제 및 매개 변수는 [Grant-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/grant-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="d36bf-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="d36bf-151">다이얼 플랜에서 설정을 보시고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="d36bf-152">다른 예제 및 매개 변수는 [Get-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d36bf-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="d36bf-153">다이얼 플랜을 삭제하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="d36bf-154">다른 예제 및 매개 변수는 [Remove-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d36bf-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="d36bf-155">효과적인 다이얼 플랜의 설정을 표시하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d36bf-156">다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan 을 참조합니다.](/powershell/module/skype/get-cseffectivetenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="d36bf-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="d36bf-157">다이얼 플랜의 효과적인 설정을 테스트하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d36bf-158">다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan 을 참조합니다.](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d36bf-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="d36bf-159">PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="d36bf-159">Using a PowerShell script</span></span>

<span data-ttu-id="d36bf-160">테넌트 다이얼 플랜을 먼저 삭제하지 않고 테넌트 다이얼 플랜과 연결된 정규화 규칙을 삭제하려면 이 규칙을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="d36bf-161">이 규칙을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 계획에 다음 정규화 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="d36bf-162">이 규칙을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 계획에서 다음 정규화 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d36bf-163">기존 정규화 규칙을 검사하고 삭제할 규칙을 결정한 다음 해당 인덱스를 사용하여 제거하려는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-163">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="d36bf-164">정규화 규칙의 배열은 인덱스 0으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-164">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="d36bf-165">인덱스 1인 3자리 정규화 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-165">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d36bf-166">이 실행을 실행하여 RedmondDialPlan 테넌트 다이얼 플랜에 부여된 모든 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="d36bf-167">이 작업을 실행하여 HostingProvider가 있는 모든 사용자에서 할당된 TenantDialPlan을 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d36bf-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="d36bf-168">조직에 대한 테넌트 다이얼 플랜으로 OPDP1이라는 기존 On-프레미스 다이얼 플랜을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-168">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="d36bf-169">먼저 프레미스 전화 걸기 계획을 .xml 파일로 저장한 다음 새 테넌트 다이얼 계획을 만드는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-169">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="d36bf-170">이 실행을 실행하여 프레미스 전화 걸기 계획을 .xml 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="d36bf-171">이 실행을 실행하여 새 테넌트 다이얼 계획을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36bf-171">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="d36bf-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d36bf-172">Related topics</span></span>

- [<span data-ttu-id="d36bf-173">다이얼 플랜이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d36bf-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="d36bf-174">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="d36bf-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="d36bf-175">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d36bf-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="d36bf-176">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="d36bf-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="d36bf-177">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="d36bf-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="d36bf-178">[긴급 호출 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d36bf-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="d36bf-179">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="d36bf-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
