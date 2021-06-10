---
title: 긴급 통화 정책 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 조직에서 긴급 호출 정책을 Microsoft Teams 조직의 사용자가 긴급 통화를 할 때 발생하는 Teams 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120569"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="07666-103">긴급 통화 정책 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07666-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="07666-104">조직에서 통화 [](set-up-calling-plans.md) 계획을 [사용하거나](direct-routing-landing-page.md)직접 라우팅을 전화 시스템 경우, 조직에서 긴급 통화 정책을 사용하여 Microsoft Teams 사용자가 긴급 전화를 걸 때 발생하는 Teams 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="07666-105">정책을 할당한 사용자가 긴급 서비스를 호출할 때 알릴 사용자와 알림을 제공하는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="07666-106">예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화에서 수신을 수신하도록 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="07666-107">관리 센터의 음성 긴급 정책으로 Microsoft Teams 또는 전화 통화를 사용하여 긴급  >   통화 정책을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07666-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="07666-108">정책은 사용자 및 네트워크 사이트에 [할당될 수 있습니다.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="07666-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="07666-109">사용자의 경우 전역(Org-wide default) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="07666-110">사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 자동으로 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="07666-111">전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="07666-112">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="07666-113">네트워크 사이트 및 사용자에게 긴급 호출 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="07666-114">사용자 지정 긴급 통화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="07666-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="07666-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="07666-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="07666-116">관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 긴급 정책으로 이동한 다음 통화 정책  >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="07666-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="07666-117">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-117">Click **Add**.</span></span>
3. <span data-ttu-id="07666-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="07666-119">조직 내 사용자(일반적으로 보안 데스크)에 긴급 호출이 걸릴 때 알리는 방법을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="07666-120">이렇게하려면 알림 **모드에서** 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="07666-121">**알림만 보내기**: Teams 채팅 메시지가 지정한 사용자 및 그룹에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="07666-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="07666-122">**음소거** 및 음소거를 할 수 없는 회의: Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹으로 보내지며 발신자 및 PSAP 연산자 간의 대화에서 수신(참여하지는 않지만)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="07666-123">**음소거로** 회의를 진행했지만 음소거를 Teams 채팅 메시지는 지정한 사용자 및 그룹으로 보내지며 발신자 및 PSAP 연산자 간의 대화를 듣고 참여하기 위해 음소거를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="07666-124">음소거 알림 모드에서  회의 중 하나를 선택한 경우  긴급 통화 알림 상자에 전화를 걸 수 있는 번호 상자에서 통화하고 긴급 통화에 참가할 사용자 또는 그룹의 PSTN 전화 번호를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="07666-125">예를 들어 조직의 보안 데스크 수를 입력합니다. 긴급 통화가 걸려오면 전화를 받고 통화를 수신할 수 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="07666-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="07666-126">모드가 음소거된 컨퍼런스로 설정되어 있지만 음소거를 하여 음소거를 할 수 있는 경우에도 PSTN 휴대폰을 음소거할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="07666-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="07666-127">조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색하여 선택하여 긴급 통화가 언제 이행될지 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="07666-128">알림은 사용자, 메일 그룹 및 보안 그룹의 전자 메일 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="07666-129">최대 50명에게 알림을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="07666-130">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="07666-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="07666-131">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="07666-131">Using PowerShell</span></span>

<span data-ttu-id="07666-132">[New-CsTeamsEmergencyCallingPolicy를 참조합니다.](/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="07666-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="07666-133">긴급 통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="07666-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="07666-134">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="07666-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="07666-135">전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07666-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="07666-136">관리 센터의 왼쪽 탐색에서 Microsoft Teams **음성** 긴급 정책으로 이동한 다음 통화 정책  >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="07666-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="07666-137">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="07666-138">원하는 내용을 변경한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="07666-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="07666-139">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="07666-139">Using PowerShell</span></span>

<span data-ttu-id="07666-140">[Set-CsTeamsEmergencyCallingPolicy를 참조합니다.](/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="07666-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="07666-141">사용자에게 사용자 지정 긴급 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="07666-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="07666-142">[Grant-CsTeamsEmergencyCallingPolicy 를 참조합니다.](/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="07666-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="07666-143">네트워크 사이트에 사용자 지정 긴급 호출 정책 할당</span><span class="sxs-lookup"><span data-stu-id="07666-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="07666-144">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 호출 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="07666-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="07666-145">다음 예제에서는 Site1 사이트에 Contoso 긴급 통화 정책 1이라는 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="07666-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="07666-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="07666-146">Related topics</span></span>

[<span data-ttu-id="07666-147">긴급 통화 라우팅 정책 관리 Teams</span><span class="sxs-lookup"><span data-stu-id="07666-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="07666-148">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="07666-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="07666-149">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="07666-149">Assign policies to your users in Teams</span></span>](assign-policies.md)