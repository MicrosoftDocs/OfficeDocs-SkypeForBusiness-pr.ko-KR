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
description: Microsoft Teams 관리 센터 또는 Windows PowerShell 사용하여 전화 요금제(PSTN 통화 전화 걸기 요금제)를 만들고 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814787"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="8712e-103">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="8712e-103">Create and manage dial plans</span></span>

<span data-ttu-id="8712e-104">조직에 대한 다이얼 플랜을 계획하고 통화 라우팅을 위해 만들어야 하는 모든 정규화 규칙을 확인한 후 다이얼 플랜을 만들 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="8712e-105">Microsoft Teams 관리 센터 또는 Windows PowerShell 요금제 만들기 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8712e-106">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8712e-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="8712e-107">다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="8712e-107">Create a dial plan</span></span>

1. <span data-ttu-id="8712e-108">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Voice Dial **요금제로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="8712e-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="8712e-109">**추가를** 클릭한 다음 다이얼 플랜의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="8712e-110">![다이얼 플랜을 만들기 위한 추가 페이지를 보여주는 스크린샷](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="8712e-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="8712e-111">전화 **걸기 계획** 세부 정보에서 사용자가 외부 선을 얻기 위해 한 자리 이상의 앞 자릿수(예: 9)에 전화를 걸 필요가 있는 경우 외부 전화 접속을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="8712e-112">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="8712e-112">To do this:</span></span>
    1. <span data-ttu-id="8712e-113">외부 전화 **걸기** 사전 상자에 외부 전화 걸기 사전을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="8712e-114">이 경우 최대 4자(#,\*, 0-9)까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="8712e-115">최적화된 **장치 전화 걸기를 니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="8712e-116">외부 전화 걸기 prefix를 지정하는 경우 조직 외부에서 전화를 걸 수 있도록 이 설정을 설정하여 해당 부호를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="8712e-117">정규화 **규칙에서** 다이얼 플랜에 대한 하나 이상의 정규화 [규칙을](what-are-dial-plans.md#normalization-rules) 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="8712e-118">각 다이얼 플랜에는 하나 이상의 정규화 규칙이 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="8712e-119">이 작업을 위해 다음 중 하나 이상을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="8712e-120">새 정규화 규칙을 만들고 다이얼 플랜에 연결하려면 추가를 클릭한 다음 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="8712e-121">다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름 왼쪽을 클릭하여 규칙을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="8712e-122">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="8712e-123">다이얼 플랜에서 정규화 규칙을 제거하려면 규칙 이름 왼쪽을 클릭하여 규칙을 선택한 다음 제거를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="8712e-124">정규화 규칙을 원하는 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="8712e-125">목록에서 **규칙의** 위치를 변경하려면 아래로 이동 또는 아래로 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="8712e-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8712e-126">Teams는 위쪽에서 아래로 정규화 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="8712e-127">전화 걸기 번호가 두 개 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 설정한 경우 덜 제한적인 규칙보다 더 제한적인 규칙이 정렬되어 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="8712e-128">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-128">Click **Save**.</span></span>
7. <span data-ttu-id="8712e-129">다이얼 플랜을 테스트하려면 테스트 다이얼 플랜에서 전화 번호를 입력한 다음 테스트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="8712e-130">다이얼 플랜 편집</span><span class="sxs-lookup"><span data-stu-id="8712e-130">Edit a dial plan</span></span>

1. <span data-ttu-id="8712e-131">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Voice Dial **요금제로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="8712e-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="8712e-132">다이얼 플랜 이름 왼쪽을 클릭하여 다이얼 플랜을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="8712e-133">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8712e-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="8712e-134">사용자에게 다이얼 플랜 할당</span><span class="sxs-lookup"><span data-stu-id="8712e-134">Assign a dial plan to users</span></span>

<span data-ttu-id="8712e-135">정책을 할당하는 방법과 동일한 방식으로 다이얼 플랜을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="8712e-136">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8712e-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="8712e-137">원격 PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="8712e-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="8712e-138">**버전 3.0 Windows PowerShell 실행 중인지 확인**</span><span class="sxs-lookup"><span data-stu-id="8712e-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="8712e-139">버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8712e-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="8712e-140">웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인</span><span class="sxs-lookup"><span data-stu-id="8712e-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="8712e-141">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치하여 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8712e-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="8712e-142">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="8712e-143">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="8712e-144">비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="8712e-145">비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688)Windows PowerShell 64비트 컴퓨터에서만 지원되는 이 모듈을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="8712e-146">메시지가 표시될 경우 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="8712e-147">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="8712e-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="8712e-148">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="8712e-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="8712e-149">시작 **Windows PowerShell.**  >  </span><span class="sxs-lookup"><span data-stu-id="8712e-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="8712e-150">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
 
    > [!NOTE]
    > <span data-ttu-id="8712e-151">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-151">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="8712e-152">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-152">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="8712e-153">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="8712e-153">Create and manage your dial plans</span></span>

<span data-ttu-id="8712e-154">단일 cmdlet 또는 PowerShell 스크립트를 사용하여 테넌트 다이얼 플랜을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-154">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="8712e-155">단일 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="8712e-155">Using single cmdlets</span></span>

- <span data-ttu-id="8712e-156">새 다이얼 플랜을 만들 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-156">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="8712e-157">다른 예제 및 매개 변수는 [New-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="8712e-157">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8712e-158">기존 다이얼 플랜의 설정을 편집하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-158">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="8712e-159">다른 예제 및 매개 변수는 [Set-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="8712e-159">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8712e-160">다이얼 플랜에 사용자를 추가하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-160">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="8712e-161">다른 예제 및 매개 변수는 [Grant-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="8712e-161">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8712e-162">다이얼 플랜에서 설정을 보기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-162">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="8712e-163">다른 예제 및 매개 변수는 [Get-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8712e-163">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="8712e-164">다이얼 플랜을 삭제하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-164">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="8712e-165">다른 예제 및 매개 변수는 [Remove-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8712e-165">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="8712e-166">유효 다이얼 플랜의 설정을 표시하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-166">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="8712e-167">다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="8712e-167">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="8712e-168">다이얼 플랜의 유효 설정을 테스트하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-168">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="8712e-169">다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8712e-169">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="8712e-170">PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="8712e-170">Using a PowerShell script</span></span>

<span data-ttu-id="8712e-171">테넌트 다이얼 플랜을 먼저 삭제할 필요 없이 테넌트 다이얼 플랜과 연결된 정규화 규칙을 삭제하려면 이 규칙을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-171">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="8712e-172">이 기능을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 플랜에 다음 정규화 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-172">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="8712e-173">이 기능을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 플랜에서 다음 정규화 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-173">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="8712e-174">기존 정규화 규칙을 검사하고 삭제할 규칙을 결정한 다음 해당 인덱스를 사용하여 제거하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-174">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="8712e-175">정규화 규칙의 배열은 인덱스 0으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-175">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="8712e-176">3자리 정규화 규칙을 제거하여 인덱스 1이 됐습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-176">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="8712e-177">이 기능을 실행하여 RedmondDialPlan 테넌트 다이얼 플랜이 부여된 모든 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-177">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="8712e-178">이 작업을 실행하여 할당된 TenantDialPlan을 HostingProvider가 있는 모든 사용자에서 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8712e-178">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="8712e-179">이 기능을 실행하여 조직의 테넌트 다이얼 플랜으로 OPDP1이라는 기존 다이얼 플랜을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-179">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="8712e-180">먼저 ,.xml 파일에는 프레미스 다이얼 플랜을 저장한 다음 이를 사용하여 새 테넌트 다이얼 플랜을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-180">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="8712e-181">이 실행을 실행하여 .xml 파일에는 프레미스 다이얼 플랜을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-181">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="8712e-182">이 기능을 실행하여 새 테넌트 다이얼 플랜을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8712e-182">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="8712e-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8712e-183">Related topics</span></span>

- [<span data-ttu-id="8712e-184">다이얼 플랜이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8712e-184">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="8712e-185">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="8712e-185">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="8712e-186">통화 요금제에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="8712e-186">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="8712e-187">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="8712e-187">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="8712e-188">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="8712e-188">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="8712e-189">[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8712e-189">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="8712e-190">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="8712e-190">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
