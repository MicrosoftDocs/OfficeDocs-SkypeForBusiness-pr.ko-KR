---
title: Microsoft 팀의 발신자 ID 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 발신자 ID 정책을 사용 하 고 관리 하 여 조직에서 팀 사용자의 발신자 ID를 변경 하거나 차단 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 67b5abef6cdbdab9a127dd2957c2fdfefbaf2927
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691424"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="eba5f-103">Microsoft 팀의 발신자 ID 정책 관리</span><span class="sxs-lookup"><span data-stu-id="eba5f-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="eba5f-104">관리자는 Microsoft 팀의 발신자 ID 정책을 사용 하 여 발신자 ID (전화 라인 ID 라고도 함)를 변경 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="eba5f-105">기본적으로 팀 사용자는 PSTN 휴대폰으로 전화를 걸거나 PSTN 발신자의 전화 번호를 볼 수 있으며,이 경우 팀에 게 전화를 걸 때 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="eba5f-106">발신자 ID 정책을 사용 하 여 조직의 팀 사용자에 대 한 대체 전화 번호를 표시 하거나 수신 번호를 표시 되지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="eba5f-107">예를 들어 사용자가 전화를 거는 경우 발신자 ID를 변경 하 여 사용자의 전화 번호 대신 조직의 기본 전화 번호를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="eba5f-108">**Voice**  >  Microsoft 팀 관리 센터에서 음성**발신자 id 정책** 으로 이동해 서 발신자 id 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="eba5f-109">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="eba5f-110">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="eba5f-111">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="eba5f-112">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="eba5f-113">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="eba5f-114">사용자 지정 발신자 ID 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="eba5f-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="eba5f-115">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **발신자 ID 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="eba5f-116">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-116">Click **Add**.</span></span> <br>
<span data-ttu-id="eba5f-117">![관리 센터의 새 발신자 ID 정책 페이지 스크린샷](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="eba5f-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="eba5f-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="eba5f-119">여기에서 원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="eba5f-120">**들어오는 발신자 Id 차단**:이 설정을 사용 하면 들어오는 전화의 발신자 id가 표시 되지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="eba5f-121">**발신자 ID 정책 재정의**: 사용자가 번호를 피호출자에 표시 하는 것과 관련 하 여 정책의 설정을 재정의할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="eba5f-122">즉, 사용자가 자신의 발신자 ID를 표시할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="eba5f-123">자세한 내용은 [아웃 바운드 발신자 ID의 최종 사용자 제어](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eba5f-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="eba5f-124">**발신자 id를 다음으로 바꿉니다**: 다음 중 하나를 선택 하 여 사용자에 게 표시할 발신자 id를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="eba5f-125">**사용자의 번호**: 사용자의 번호를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="eba5f-126">**서비스 번호**: 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="eba5f-127">**익명**: 발신자 ID를 익명으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="eba5f-128">**발신자 id를 다음 서비스 번호로 바꾸기**: 사용자의 발신자 id를 바꿀 서비스 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="eba5f-129">이 옵션은 **발신자 ID를 (으)로 바꾸기**에서 **서비스 번호** 를 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="eba5f-130">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="eba5f-131">발신자 ID 정책 편집</span><span class="sxs-lookup"><span data-stu-id="eba5f-131">Edit a caller ID policy</span></span>

<span data-ttu-id="eba5f-132">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="eba5f-133">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **발신자 ID 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="eba5f-134">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="eba5f-135">원하는 설정을 변경한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="eba5f-136">사용자에 게 사용자 지정 발신자 ID 정책 할당</span><span class="sxs-lookup"><span data-stu-id="eba5f-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="eba5f-137">Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 그룹의 사용자에 게 보안 그룹 또는 메일 그룹과 같은 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="eba5f-138">사용자에 게 사용자 지정 발신자 줄 ID 정책 할당</span><span class="sxs-lookup"><span data-stu-id="eba5f-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="eba5f-139">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="eba5f-140">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="eba5f-141">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="eba5f-142">**발신자 ID 정책**에서 할당할 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="eba5f-143">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="eba5f-144">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="eba5f-145">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="eba5f-146">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="eba5f-147">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="eba5f-148">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="eba5f-149">**Microsoft 팀 관리 센터**  >  **음성**  >  **발신자 ID 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="eba5f-150">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="eba5f-151">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="eba5f-152">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="eba5f-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="eba5f-153">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="eba5f-154">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="eba5f-155">그룹의 사용자에 게 사용자 지정 발신자 ID 정책 할당</span><span class="sxs-lookup"><span data-stu-id="eba5f-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="eba5f-156">이미 식별 한 여러 사용자에 게 사용자 지정 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="eba5f-157">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="eba5f-158">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="eba5f-159">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eba5f-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="eba5f-160">이 예제에서는 사용자 지정 호출자 덮개 정책을 Contoso 지원 그룹의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="eba5f-161">먼저 [모든 Microsoft 365 또는 Office 365 서비스에 연결의 단계를 단일 Windows powershell 창에](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="eba5f-162">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="eba5f-163">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="eba5f-164">그룹의 모든 사용자를 특정 발신자 ID 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="eba5f-165">이 예제에서는 발신자 ID 정책을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="eba5f-166">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba5f-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="eba5f-167">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eba5f-167">Related topics</span></span>

- [<span data-ttu-id="eba5f-168">새로운 CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="eba5f-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="eba5f-169">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="eba5f-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
