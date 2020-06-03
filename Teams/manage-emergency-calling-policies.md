---
title: Microsoft 팀에서 긴급 통화 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 긴급 전화 정책을 사용 하 고 관리 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행할 작업을 정의 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98d6fb5eba98701cddccb808e5670fb34a00efbf
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539485"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="3d439-103">Microsoft 팀에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3d439-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="3d439-104">조직에서 [통화 계획](set-up-calling-plans.md) 또는 배포 된 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)사용 하는 경우 Microsoft 팀에서 비상 전화 정책을 사용 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행 되는 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="3d439-105">정책을 할당할 사용자가 응급 서비스를 호출할 때 알릴 사람과 알림을 받을 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="3d439-106">예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 전화를 수신 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="3d439-107">**Voice**  >  Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 음성**응급 정책** 으로 이동해 서 긴급 통화 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="3d439-108">사용자 및 [네트워크 사이트](cloud-voice-network-settings.md)에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="3d439-109">사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3d439-110">사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3d439-111">전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d439-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="3d439-112">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="3d439-113">긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="3d439-114">사용자 지정 비상 통화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3d439-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d439-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3d439-116">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d439-117">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-117">Click **Add**.</span></span>
3. <span data-ttu-id="3d439-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="3d439-119">긴급 통화가 이루어질 때 조직의 사용자에 게 일반적으로 보안 데스크에 알리는 방법을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="3d439-120">이렇게 하려면 **알림 모드**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="3d439-121">**알림만 보내기**: 팀 채팅 메시지가 지정 된 사용자 및 그룹에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="3d439-122">**Conferenced에는 있지만 음소거 되어**있습니다. 지정 하는 사용자 및 그룹에 팀 채팅 메시지가 전송 되며, 호출자와 psap 연산자 간에 대화에 참여 하지 않고이를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="3d439-123">**Conferenced는 음소거 됨** **(곧 출시 예정)**: 지정 된 사용자 및 그룹에 게 팀 채팅 메시지를 보내고,이를 수신 대기 하도록 음소거 해제 하 고 호출자와 psap 연산자 간에 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="3d439-124">**Conferenced in (음소거** 알림 모드)을 선택한 경우에는 비상 전화를 **걸 번호** 상자에서 사용자 또는 그룹의 PSTN 전화 번호를 입력 하 여 비상 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="3d439-125">예를 들어, 긴급 통화를 할 때 전화를 받을 수 있는 조직의 보안 데스크 번호를 입력 하 고 통화를 수신 대기 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="3d439-126">조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색 하 고 선택 하 여 긴급 통화가 발생 한 경우 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="3d439-127">알림은 사용자, 메일 그룹, 보안 그룹의 전자 메일 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="3d439-128">최대 50 명의 사용자에 게 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="3d439-129">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d439-130">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-130">Using PowerShell</span></span>

<span data-ttu-id="3d439-131">[새로운 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d439-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="3d439-132">긴급 통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="3d439-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d439-133">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3d439-134">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="3d439-135">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d439-136">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3d439-137">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d439-138">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-138">Using PowerShell</span></span>

<span data-ttu-id="3d439-139">[Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d439-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="3d439-140">사용자에 게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3d439-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3d439-141">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3d439-142">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="3d439-143">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3d439-144">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="3d439-145">**비상 전화 정책**에서 할당 하려는 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="3d439-146">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="3d439-147">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="3d439-148">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="3d439-149">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="3d439-150">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="3d439-151">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3d439-152">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="3d439-153">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3d439-154">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="3d439-155">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="3d439-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3d439-156">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3d439-157">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3d439-158">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="3d439-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="3d439-159">사용자에 게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3d439-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="3d439-160">[허용-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d439-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="3d439-161">사용자 지정 긴급 통화 정책을 그룹의 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="3d439-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="3d439-162">이미 확인 한 여러 사용자에 게 사용자 지정 비상 전화 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="3d439-163">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="3d439-164">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="3d439-165">이 예제에서는 운영 긴급 호출 정책 이라고 하는 정책을 Contoso Operations group의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="3d439-166">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="3d439-167">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="3d439-168">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3d439-169">특정 팀 정책에 그룹의 모든 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="3d439-170">이 예제에서는 운영 긴급 통화 라우팅 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="3d439-171">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="3d439-172">네트워크 사이트에 사용자 지정 비상 통화 정책 지정</span><span class="sxs-lookup"><span data-stu-id="3d439-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="3d439-173">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 비상 전화 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="3d439-174">다음 예제에서는 Site1 사이트에 Contoso 비상 통화 정책 1 이라는 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d439-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="3d439-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d439-175">Related topics</span></span>

- [<span data-ttu-id="3d439-176">팀에서 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3d439-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="3d439-177">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="3d439-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="3d439-178">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3d439-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
