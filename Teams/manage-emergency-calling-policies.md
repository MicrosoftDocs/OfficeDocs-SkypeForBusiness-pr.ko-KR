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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀의 동적 E911 기능에 대 한 긴급 통화 정책을 사용 하 고 관리 하는 방법에 대해 알아봅니다.
f1keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 4a1846217734142388fdf3466f68ccadea49c829
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639360"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="e4ef5-103">Microsoft 팀에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e4ef5-103">Manage emergency calling policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e4ef5-104">조직에서 통화 계획 또는 배포 된 전화 시스템 직접 라우팅을 사용 하는 경우 Microsoft 팀에서 비상 전화 정책을 사용 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행 되는 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="e4ef5-105">정책을 할당할 사용자가 응급 서비스를 호출할 때 알릴 사람과 알림을 받을 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="e4ef5-106">예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 전화를 수신 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="e4ef5-107">Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 **음성** > **응급 정책** 으로 이동해 서 긴급 통화 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e4ef5-108">사용자 및 [네트워크 사이트](location-based-routing-terminology.md)에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-108">The policies can be assigned to users and [network sites](location-based-routing-terminology.md).</span></span>

<span data-ttu-id="e4ef5-109">사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e4ef5-110">사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e4ef5-111">전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e4ef5-112">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e4ef5-113">긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="e4ef5-114">사용자 지정 비상 통화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e4ef5-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e4ef5-115">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e4ef5-116">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e4ef5-117">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-117">Click **Add**.</span></span>
3. <span data-ttu-id="e4ef5-118">정책의 이름 및 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e4ef5-119">긴급 통화가 이루어질 때 조직의 사용자에 게 일반적으로 보안 데스크에 알리는 방법을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="e4ef5-120">이렇게 하려면 **알림 모드**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="e4ef5-121">**알림만**: 지정 된 사용자 및 그룹에 게 팀 채팅 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-121">**Notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="e4ef5-122">**Conferenced에는 있지만 음소거 되어**있습니다. 지정 하는 사용자 및 그룹에 팀 채팅 메시지가 전송 되며, 호출자와 psap 연산자 간에 대화에 참여 하지 않고이를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="e4ef5-123">**Conferenced in (음소거 됨** 알림 모드)을 선택한 경우에는 **알림 전화 접속 번호** 상자에서 사용자 또는 그룹의 PSTN 전화 번호를 입력 하 여 비상 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-123">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="e4ef5-124">예를 들어 조직의 보안 데스크 번호를 입력 하 고, 긴급 통화를 할 때 전화를 받을 수 있으며, 전화를 걸거나이에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-124">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in or participate in the call.</span></span>
6. <span data-ttu-id="e4ef5-125">조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색 하 고 선택 하 여 긴급 통화가 발생 한 경우 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-125">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="e4ef5-126">알림은 사용자, 메일 그룹, 보안 그룹의 전자 메일 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-126">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="e4ef5-127">최대 50 명의 사용자에 게 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-127">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="e4ef5-128">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-128">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e4ef5-129">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-129">Using PowerShell</span></span>

<span data-ttu-id="e4ef5-130">[새로운 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-130">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="e4ef5-131">긴급 통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="e4ef5-131">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e4ef5-132">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-132">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e4ef5-133">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-133">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e4ef5-134">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e4ef5-135">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-135">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e4ef5-136">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e4ef5-137">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-137">Using PowerShell</span></span>

<span data-ttu-id="e4ef5-138">[Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-138">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="e4ef5-139">사용자에 게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e4ef5-139">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e4ef5-140">Microsoft 팀 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-140">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e4ef5-141">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e4ef5-142">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-142">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e4ef5-143">**비상 전화 정책**에서 할당 하려는 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-143">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="e4ef5-144">사용자 지정 팀 정책을 한 번에 여러 사용자에 게 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-144">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e4ef5-145">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-145">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e4ef5-146">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-146">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e4ef5-147">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-147">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e4ef5-148">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-148">Select **Manage users**.</span></span>
4. <span data-ttu-id="e4ef5-149">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-149">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e4ef5-150">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-150">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e4ef5-151">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-151">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e4ef5-152">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="e4ef5-152">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="e4ef5-153">사용자에 게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e4ef5-153">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="e4ef5-154">[허용-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-154">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="e4ef5-155">사용자 지정 긴급 통화 정책을 그룹의 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="e4ef5-155">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="e4ef5-156">이미 확인 한 여러 사용자에 게 사용자 지정 비상 전화 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-156">You may want to assign a custom emergency calling policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e4ef5-157">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e4ef5-158">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="e4ef5-159">이 예제에서는 운영 긴급 호출 정책 이라고 하는 정책을 Contoso Operations group의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-159">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e4ef5-160">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-160">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e4ef5-161">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-161">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="e4ef5-162">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-162">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e4ef5-163">특정 팀 정책에 그룹의 모든 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-163">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="e4ef5-164">이 예제에서는 운영 긴급 통화 라우팅 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-164">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="e4ef5-165">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-165">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="e4ef5-166">네트워크 사이트에 사용자 지정 비상 통화 정책 지정</span><span class="sxs-lookup"><span data-stu-id="e4ef5-166">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="e4ef5-167">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 비상 전화 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-167">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="e4ef5-168">다음 예제에서는 Site1 사이트에 Contoso 비상 통화 정책 1 이라는 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4ef5-168">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a><span data-ttu-id="e4ef5-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e4ef5-169">Related topics</span></span>

- [<span data-ttu-id="e4ef5-170">팀에서 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e4ef5-170">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="e4ef5-171">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="e4ef5-171">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
