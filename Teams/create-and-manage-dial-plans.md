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
ms.openlocfilehash: f94c847f5c75e793856c0975678e2806629e2dcd
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282365"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="0e13d-103">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="0e13d-103">Create and manage dial plans</span></span>

<span data-ttu-id="0e13d-104">조직의 전화 걸기 계획을 계획하고 통화 라우팅을 위해 만들어야 하는 모든 정규화 규칙을 확인한 후 다이얼 계획을 만들 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="0e13d-105">유효한 라이선스가 있는 관리자 계정으로 Teams 관리 센터 또는 Microsoft Teams Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0e13d-106">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="0e13d-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="0e13d-107">다이얼 요금제 만들기</span><span class="sxs-lookup"><span data-stu-id="0e13d-107">Create a dial plan</span></span>

1. <span data-ttu-id="0e13d-108">관리 센터의 왼쪽 Microsoft Teams 음성 전화 걸기 계획으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="0e13d-109">추가 **를** 클릭한 다음 다이얼 요금제에 대한 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="0e13d-110">![다이얼 요금제 만들기를 위한 추가 페이지를 보여주는 스크린샷](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="0e13d-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="0e13d-111">전화 **걸기 계획 세부** 정보에서 사용자가 외부 줄을 얻기 위해 하나 이상의 앞자리(예: 9)에 전화를 걸 필요가 있는 경우 외부 전화 걸기 전단을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="0e13d-112">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="0e13d-112">To do this:</span></span>
    1. <span data-ttu-id="0e13d-113">외부 전화 **걸기** 연사 상자에 외부 전화 접속 도두사에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="0e13d-114">이 연결선은 최대 4자(#,\*, 0-9)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="0e13d-115">최적화된 **디바이스 전화 걸기를 켜기**</span><span class="sxs-lookup"><span data-stu-id="0e13d-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="0e13d-116">외부 전화 걸기 전신을 지정하는 경우 조직 외부에서 호출할 수 있도록 이 설정을 켜서 도우미를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="0e13d-117">정규화 **규칙에서** 다이얼 계획에 대해 하나 이상의 정규화 [규칙을](what-are-dial-plans.md#normalization-rules) 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="0e13d-118">각 다이얼 계획에는 하나 이상의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="0e13d-119">이렇게 하여 다음 중 하나 이상을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="0e13d-120">새 정규화 규칙을 만들고 다이얼 계획과 연결하려면 **추가를** 클릭한 다음 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="0e13d-121">다이얼 계획과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름의 왼쪽을 클릭하여 규칙을 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="0e13d-122">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="0e13d-123">다이얼 계획에서 정규화 규칙을 제거하려면 규칙 이름의 왼쪽을 클릭하여 규칙을 선택한 다음 **제거를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="0e13d-124">정규화 규칙을 원하는 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="0e13d-125">이동 **또는** **아래로 이동을** 클릭하여 목록의 규칙 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e13d-126">Teams 위쪽에서 정규화 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0e13d-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="0e13d-127">전화 걸기 번호가 두 개 이상의 정규화 규칙과 일치하도록 전화 걸기 계획을 설정한 경우 더 제한적인 규칙이 덜 제한적인 규칙보다 정렬되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="0e13d-128">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-128">Click **Save**.</span></span>
7. <span data-ttu-id="0e13d-129">전화 걸기 계획을 테스트하려면 전화 걸기 계획에서 **전화** 번호를 입력한 다음 테스트 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="0e13d-130">다이얼 플랜 편집</span><span class="sxs-lookup"><span data-stu-id="0e13d-130">Edit a dial plan</span></span>

1. <span data-ttu-id="0e13d-131">관리 센터의 왼쪽 Microsoft Teams 음성 전화 걸기 계획으로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="0e13d-132">다이얼 플랜 이름의 왼쪽을 클릭하여 다이얼 계획을 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0e13d-133">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0e13d-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="0e13d-134">사용자에게 전화 걸기 요금제 할당</span><span class="sxs-lookup"><span data-stu-id="0e13d-134">Assign a dial plan to users</span></span>

<span data-ttu-id="0e13d-135">정책을 할당하는 방식과 동일한 방식으로 다이얼 플랜을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="0e13d-136">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="0e13d-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="0e13d-137">PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="0e13d-137">Start PowerShell</span></span>
- <span data-ttu-id="0e13d-138">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="0e13d-139">다이얼 요금제 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="0e13d-139">Create and manage your dial plans</span></span>

<span data-ttu-id="0e13d-140">단일 cmdlet 또는 PowerShell 스크립트를 사용하여 테넌트 다이얼 계획을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="0e13d-141">단일 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="0e13d-141">Using single cmdlets</span></span>

- <span data-ttu-id="0e13d-142">새 다이얼 계획을 만들 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="0e13d-143">다른 예제 및 매개 변수는 [New-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/new-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="0e13d-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0e13d-144">기존 다이얼 플랜의 설정을 편집하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="0e13d-145">다른 예제 및 매개 변수는 [Set-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/set-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="0e13d-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0e13d-146">다이얼 플랜에 사용자를 추가하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="0e13d-147">다른 예제 및 매개 변수는 [Grant-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/grant-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="0e13d-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0e13d-148">다이얼 플랜에서 설정을 보시고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="0e13d-149">다른 예제 및 매개 변수는 [Get-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e13d-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="0e13d-150">다이얼 플랜을 삭제하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="0e13d-151">다른 예제 및 매개 변수는 [Remove-CsTenantDialPlan 을 참조합니다.](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e13d-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="0e13d-152">효과적인 다이얼 플랜의 설정을 표시하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="0e13d-153">다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan 을 참조합니다.](/powershell/module/skype/get-cseffectivetenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="0e13d-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="0e13d-154">다이얼 플랜의 효과적인 설정을 테스트하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="0e13d-155">다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan 을 참조합니다.](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e13d-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="0e13d-156">PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="0e13d-156">Using a PowerShell script</span></span>

<span data-ttu-id="0e13d-157">테넌트 다이얼 플랜을 먼저 삭제하지 않고 테넌트 다이얼 플랜과 연결된 정규화 규칙을 삭제하려면 이 규칙을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="0e13d-158">이 규칙을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 계획에 다음 정규화 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="0e13d-159">이 규칙을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 계획에서 다음 정규화 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="0e13d-160">기존 정규화 규칙을 검사하고 삭제할 규칙을 결정한 다음 해당 인덱스를 사용하여 제거하려는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-160">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="0e13d-161">정규화 규칙의 배열은 인덱스 0으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-161">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="0e13d-162">인덱스 1인 3자리 정규화 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-162">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="0e13d-163">이 실행을 실행하여 RedmondDialPlan 테넌트 다이얼 플랜에 부여된 모든 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="0e13d-164">이 작업을 실행하여 HostingProvider가 있는 모든 사용자에서 할당된 TenantDialPlan을 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0e13d-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="0e13d-165">조직에 대한 테넌트 다이얼 플랜으로 OPDP1이라는 기존 On-프레미스 다이얼 플랜을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-165">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="0e13d-166">먼저 프레미스 전화 걸기 계획을 .xml 파일로 저장한 다음 새 테넌트 다이얼 계획을 만드는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-166">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="0e13d-167">이 실행을 실행하여 프레미스 전화 걸기 계획을 .xml 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="0e13d-168">이 실행을 실행하여 새 테넌트 다이얼 계획을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e13d-168">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="0e13d-169">관련 주제</span><span class="sxs-lookup"><span data-stu-id="0e13d-169">Related topics</span></span>

- [<span data-ttu-id="0e13d-170">다이얼 플랜이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0e13d-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="0e13d-171">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="0e13d-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="0e13d-172">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="0e13d-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="0e13d-173">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="0e13d-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="0e13d-174">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="0e13d-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="0e13d-175">[긴급 호출 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0e13d-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="0e13d-176">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="0e13d-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
