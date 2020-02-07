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
description: 통화 다이얼 플랜을 만들고 관리 하는 방법 (PSTN 통화 다이얼 플랜)과이를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 774b0a78f39b91b634ed0833be3497935cb25c4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826926"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="54626-103">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="54626-103">Create and manage dial plans</span></span>

<span data-ttu-id="54626-104">조직에 대 한 다이얼 플랜을 계획 하 고 통화 라우팅에 대해 만들어야 하는 모든 정규화 규칙을 파악 한 후에는 다이얼 플랜을 만들 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54626-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="54626-105">Microsoft 팀 관리 센터 또는 Windows PowerShell을 사용 하 여 다이얼 플랜을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54626-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="54626-106">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="54626-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="54626-107">다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="54626-107">Create a dial plan</span></span>

1. <span data-ttu-id="54626-108">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="54626-109">**추가**를 클릭 한 다음 다이얼 플랜의 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="54626-110">![다이얼 플랜을 만들기 위한 추가 페이지를 보여 주는 스크린샷](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="54626-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="54626-111">**다이얼 플랜 세부 정보**아래에서 사용자가 하나 이상의 추가 선행 번호 (예: 9)를 입력 하 여 외부 회선을 확보 해야 하는 경우 외부 전화 걸기 접두사를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="54626-112">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="54626-112">To do this:</span></span>
    1. <span data-ttu-id="54626-113">**외부 전화 걸기 접두 번호** 상자에 외부 전화 걸기 접두사를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="54626-114">접두사는 최대 4 자 (#, \*, 0-9)로 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54626-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="54626-115">최적화 된 **장치 전화 걸기를**켭니다.</span><span class="sxs-lookup"><span data-stu-id="54626-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="54626-116">외부 전화 걸기 접두사를 지정 하는 경우에는이 설정을 사용 하 여 사용자가 조직 외부에서 전화를 걸 수 있도록 접두사를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="54626-117">**정규화 규칙**에서 다이얼 플랜에 하나 이상의 [정규화 규칙](what-are-dial-plans.md#normalization-rules) 을 구성 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="54626-118">각 다이얼 플랜에는 하나 이상의 정규화 규칙이 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="54626-119">이렇게 하려면 다음 중 하나 이상을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="54626-120">새 정규화 규칙을 만들어 다이얼 플랜에 연결 하려면 **추가**를 클릭 한 다음 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="54626-121">다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름 왼쪽에 있는을 클릭 하 여 규칙을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="54626-122">원하는 대로 변경한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="54626-123">다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름 왼쪽에 있는을 클릭 하 여 규칙을 선택한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="54626-124">정규화 규칙을 원하는 순서 대로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="54626-125">**위로 이동** 또는 **아래로 이동을** 클릭 하 여 목록에서 규칙의 위치를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54626-126">팀은 정규화 규칙 목록을 위에서 아래로 이동 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="54626-127">전화 거는 번호가 둘 이상의 정규화 규칙을 사용할 수 있도록 다이얼 플랜을 설정 하는 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 위에 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="54626-128">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-128">Click **Save**.</span></span>
7. <span data-ttu-id="54626-129">다이얼 플랜을 테스트 하려면 **다이얼 플랜 테스트**에서 전화 번호를 입력 한 다음 **테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="54626-130">다이얼 플랜 편집</span><span class="sxs-lookup"><span data-stu-id="54626-130">Edit a dial plan</span></span>

1. <span data-ttu-id="54626-131">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="54626-132">다이얼 플랜 이름 왼쪽을 클릭 하 여 다이얼 플랜을 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="54626-133">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="54626-134">다이얼 플랜에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="54626-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="54626-135">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="54626-136">다이얼 플랜 이름 왼쪽을 클릭 하 여 다이얼 플랜을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-136">Select the dial plan by clicking to the left of the dial plan name.</span></span>
3. <span data-ttu-id="54626-137">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="54626-138">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="54626-139">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="54626-140">사용자 추가를 마쳤으면 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-140">When you're finished adding users, select **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="54626-141">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="54626-141">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="54626-142">원격 PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="54626-142">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="54626-143">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="54626-143">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="54626-144">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-144">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="54626-145">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-145">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="54626-146">버전 3.0 이상이 없는 경우 Windows PowerShell에 업데이트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-146">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="54626-147">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-147">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="54626-148">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-148">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="54626-149">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-149">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="54626-150">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54626-150">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="54626-151">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-151">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="54626-152">자세한 내용은 [단일 Windows PowerShell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-152">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="54626-153">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="54626-153">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="54626-154">**Windows PowerShell** **시작** > 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-154">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="54626-155">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-155">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54626-156">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54626-156">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="54626-157">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="54626-157">Create and manage your dial plans</span></span>

<span data-ttu-id="54626-158">단일 cmdlet 또는 PowerShell 스크립트를 사용 하 여 테 넌 트 다이얼 플랜을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54626-158">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="54626-159">단일 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="54626-159">Using single cmdlets</span></span>

- <span data-ttu-id="54626-160">새 다이얼 플랜을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-160">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="54626-161">다른 예제 및 매개 변수는 [New-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-161">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="54626-162">기존 다이얼 플랜의 설정을 편집 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-162">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="54626-163">다른 예제 및 매개 변수는 [Set-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-163">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="54626-164">다이얼 플랜에 사용자를 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-164">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="54626-165">다른 예제 및 매개 변수는 [-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-165">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="54626-166">다이얼 플랜에 대 한 설정을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-166">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="54626-167">다른 예제 및 매개 변수는 [Get-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-167">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="54626-168">다이얼 플랜을 삭제 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-168">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="54626-169">다른 예제 및 매개 변수는 [제거-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-169">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="54626-170">유효 다이얼 플랜의 설정을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-170">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="54626-171">다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-171">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="54626-172">다이얼 플랜의 유효 설정을 테스트 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-172">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="54626-173">다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="54626-173">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="54626-174">PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="54626-174">Using a PowerShell script</span></span>

<span data-ttu-id="54626-175">이 작업을 실행 하 여 테 넌 트 다이얼 플랜을 먼저 삭제할 필요 없이 테 넌 트 다이얼 플랜에 연결 된 정규화 규칙을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-175">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="54626-176">이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에 다음 정규화 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-176">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="54626-177">이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에서 다음 정규화 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-177">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="54626-178">다음을 실행 하 여 기존 정규화 규칙을 검사 하 고 삭제 하려는 항목을 결정 한 다음 인덱스를 사용 하 여 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-178">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="54626-179">정규화 규칙 배열은 index 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-179">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="54626-180">3 자리 정규화 규칙을 제거 하 여 인덱스 1을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-180">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="54626-181">이를 실행 하 여 RedmondDialPlan 테 넌 트 다이얼 플랜을 부여한 모든 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="54626-181">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="54626-182">이를 실행 하 여 sipfed.online.lync.com의 HostingProvider 있는 모든 사용자가 할당 된 TenantDialPlan 플랜을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-182">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="54626-183">OPDP1 라는 기존 온-프레미스 다이얼 플랜을 조직의 테 넌 트 다이얼 플랜으로 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-183">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="54626-184">먼저 .xml 파일에 온-프레미스 다이얼 플랜을 저장 한 다음이를 사용 하 여 새 테 넌 트 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54626-184">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="54626-185">이를 실행 하 여 온-프레미스 다이얼 플랜을 .xml 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-185">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="54626-186">새 테 넌 트 다이얼 플랜을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="54626-186">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="54626-187">관련 항목</span><span class="sxs-lookup"><span data-stu-id="54626-187">Related topics</span></span>

- [<span data-ttu-id="54626-188">다이얼 플랜이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="54626-188">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="54626-189">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="54626-189">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="54626-190">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="54626-190">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="54626-191">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="54626-191">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="54626-192">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="54626-192">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="54626-193">[비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="54626-193">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="54626-194">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="54626-194">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
