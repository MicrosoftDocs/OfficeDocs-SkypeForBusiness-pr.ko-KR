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
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 긴급 전화 정책을 사용 하 고 관리 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행할 작업을 정의 하는 방법에 대해 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217669"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="6eacb-103">Microsoft 팀에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6eacb-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="6eacb-104">조직에서 [통화 계획](set-up-calling-plans.md) 또는 배포 된 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)사용 하는 경우 Microsoft 팀에서 비상 전화 정책을 사용 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행 되는 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="6eacb-105">정책을 할당할 사용자가 응급 서비스를 호출할 때 알릴 사람과 알림을 받을 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="6eacb-106">예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 전화를 수신 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="6eacb-107">**Voice**  >  Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 음성**응급 정책** 으로 이동해 서 긴급 통화 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="6eacb-108">사용자 및 [네트워크 사이트](cloud-voice-network-settings.md)에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="6eacb-109">사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6eacb-110">사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6eacb-111">전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="6eacb-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="6eacb-112">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="6eacb-113">긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="6eacb-114">사용자 지정 비상 통화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6eacb-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6eacb-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6eacb-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6eacb-116">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="6eacb-117">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-117">Click **Add**.</span></span>
3. <span data-ttu-id="6eacb-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="6eacb-119">긴급 통화가 이루어질 때 조직의 사용자에 게 일반적으로 보안 데스크에 알리는 방법을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="6eacb-120">이렇게 하려면 **알림 모드**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="6eacb-121">**알림만 보내기**: 팀 채팅 메시지가 지정 된 사용자 및 그룹에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="6eacb-122">**Conferenced에는 있지만 음소거 되어**있습니다. 지정 하는 사용자 및 그룹에 팀 채팅 메시지가 전송 되며, 호출자와 psap 연산자 간에 대화에 참여 하지 않고이를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="6eacb-123">**Conferenced는 음소거 됨** **(곧 출시 예정)**: 지정 된 사용자 및 그룹에 게 팀 채팅 메시지를 보내고,이를 수신 대기 하도록 음소거 해제 하 고 호출자와 psap 연산자 간에 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="6eacb-124">**Conferenced in (음소거** 알림 모드)을 선택한 경우에는 비상 전화를 **걸 번호** 상자에서 사용자 또는 그룹의 PSTN 전화 번호를 입력 하 여 비상 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="6eacb-125">예를 들어, 긴급 통화를 할 때 전화를 받을 수 있는 조직의 보안 데스크 번호를 입력 하 고 통화를 수신 대기 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="6eacb-126">조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색 하 고 선택 하 여 긴급 통화가 발생 한 경우 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="6eacb-127">알림은 사용자, 메일 그룹, 보안 그룹의 전자 메일 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="6eacb-128">최대 50 명의 사용자에 게 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="6eacb-129">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6eacb-130">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6eacb-130">Using PowerShell</span></span>

<span data-ttu-id="6eacb-131">[새로운 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6eacb-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="6eacb-132">긴급 통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="6eacb-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6eacb-133">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6eacb-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6eacb-134">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="6eacb-135">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="6eacb-136">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6eacb-137">원하는 대로 변경한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6eacb-138">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6eacb-138">Using PowerShell</span></span>

<span data-ttu-id="6eacb-139">[Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6eacb-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="6eacb-140">사용자에 게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6eacb-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="6eacb-141">[허용-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6eacb-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="6eacb-142">네트워크 사이트에 사용자 지정 비상 통화 정책 지정</span><span class="sxs-lookup"><span data-stu-id="6eacb-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="6eacb-143">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 비상 전화 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="6eacb-144">다음 예제에서는 Site1 사이트에 Contoso 비상 통화 정책 1 이라는 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eacb-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="6eacb-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6eacb-145">Related topics</span></span>

[<span data-ttu-id="6eacb-146">팀에서 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6eacb-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="6eacb-147">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="6eacb-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="6eacb-148">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6eacb-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
