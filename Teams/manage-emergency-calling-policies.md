---
title: Microsoft Teams에서 긴급 통화 정책 관리
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
description: Microsoft Teams에서 긴급 통화 정책을 사용 및 관리하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 일들을 정의하는 방법을 배워야 합니다.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1e516252317a0e5f14e705b674255048fb3defb5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804688"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="26d9b-103">Microsoft Teams에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="26d9b-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="26d9b-104">조직에서 통화 [](set-up-calling-plans.md) 요금제 또는 [](direct-routing-landing-page.md)배포된 전화 시스템 직접 라우팅을 사용하는 경우 Microsoft Teams의 긴급 통화 정책을 사용하여 조직의 Teams 사용자가 긴급 통화를 할 때 발생하는 일에 대해 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="26d9b-105">정책이 할당된 사용자가 긴급 서비스를 호출할 때 알릴 사용자 및 알림을 제공하는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="26d9b-106">예를 들어 조직의 보안 센터에 자동으로 알리고 긴급 통화를 듣도록 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="26d9b-107">Microsoft Teams 관리 센터에서 음성 긴급 정책으로 또는 통화를 사용하여 긴급  >   통화 정책을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26d9b-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="26d9b-108">정책은 사용자 및 네트워크 사이트에 [할당할 수 있습니다.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="26d9b-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="26d9b-109">사용자의 경우 전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="26d9b-110">사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역 정책을 자동으로 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="26d9b-111">전역 정책에서 설정을 편집할 수 있지만 이름을 변경하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="26d9b-112">네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="26d9b-113">네트워크 사이트 및 사용자에게 긴급 통화 정책을 할당한 경우 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="26d9b-114">사용자 지정 긴급 통화 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="26d9b-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26d9b-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26d9b-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="26d9b-116">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 정책  >   **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="26d9b-117">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26d9b-117">Click **Add**.</span></span>
3. <span data-ttu-id="26d9b-118">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="26d9b-119">응급 전화가 걸려 오면 조직 내 다른 사용자에게 일반적으로 보안 센터에 알리는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="26d9b-120">이렇게하려면 알림 모드에서 **다음** 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="26d9b-121">**알림 보내기만:** 지정한 사용자 및 그룹에 Teams 채팅 메시지가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="26d9b-122">**전화 회의 중이지만** 음소거됩니다. Teams 채팅 메시지는 사용자가 지정한 사용자 및 그룹으로 보내지며 발신자와 PSAP 운영자 간의 대화에서 듣기(참여하지는 못합니다)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="26d9b-123">**전화 회의가** 진행 중이면(출시 **예정)** Teams 채팅 메시지가 지정한 사용자 및 그룹에게 전송됩니다. 발신자 및 PSAP 운영자 간의 대화를 듣고 참여하기 위해 음성을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="26d9b-124">전화 회의를  선택했지만 음소거된 알림 모드인 경우 긴급 통화 알림 상자에 전화를 걸 번호에 사용자 또는 그룹의 PSTN 전화 번호를 입력하여 전화를 걸고 긴급 통화에 참가할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="26d9b-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="26d9b-125">예를 들어, 조직의 보안 데스크 번호를 입력합니다. 긴급 전화가 걸려오면 전화를 받고 통화를 들을 수 있는 사람.</span><span class="sxs-lookup"><span data-stu-id="26d9b-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="26d9b-126">긴급 전화가 걸려 오면 알릴 하나 이상의 사용자 또는 그룹(예: 조직의 보안 데스크)을 검색하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="26d9b-127">알림은 사용자, 메일 그룹 및 보안 그룹의 전자 메일 주소로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="26d9b-128">최대 50명까지 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="26d9b-129">적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26d9b-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26d9b-130">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26d9b-130">Using PowerShell</span></span>

<span data-ttu-id="26d9b-131">[New-CsTeamsEmergencyCallingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="26d9b-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="26d9b-132">긴급 통화 정책 편집</span><span class="sxs-lookup"><span data-stu-id="26d9b-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26d9b-133">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26d9b-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="26d9b-134">전역 정책 또는 만든 모든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="26d9b-135">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 음성 응급 정책으로 이동한 다음 통화 정책  >   **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="26d9b-136">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26d9b-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="26d9b-137">원하는 내용을 변경한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26d9b-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26d9b-138">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26d9b-138">Using PowerShell</span></span>

<span data-ttu-id="26d9b-139">[Set-CsTeamsEmergencyCallingPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="26d9b-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="26d9b-140">사용자에게 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26d9b-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="26d9b-141">[Grant-CsTeamsEmergencyCallingPolicy도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="26d9b-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="26d9b-142">네트워크 사이트에 사용자 지정 긴급 통화 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26d9b-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="26d9b-143">[Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 네트워크 사이트에 긴급 통화 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="26d9b-144">다음 예제에서는 Contoso 긴급 통화 정책 1이라는 정책을 Site1 사이트에 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="26d9b-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="26d9b-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="26d9b-145">Related topics</span></span>

[<span data-ttu-id="26d9b-146">Teams에서 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="26d9b-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="26d9b-147">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="26d9b-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="26d9b-148">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26d9b-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
