---
title: 프레미스 Teams 배포에서 비즈니스용 Skype 도구
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype 업그레이드를 위한 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437635"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="bf773-103">IT 관리자를 위해 Teams &mdash; 도구</span><span class="sxs-lookup"><span data-stu-id="bf773-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="bf773-104">이 문서에서는 이 문서에서 Teams 업그레이드하기 위한 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="bf773-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="bf773-105">업그레이드를 시작하기 전에 Microsoft는 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="bf773-106">Teams 및 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf773-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="bf773-107">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="bf773-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="bf773-108">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="bf773-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="bf773-109">업그레이드를 관리하는 도구</span><span class="sxs-lookup"><span data-stu-id="bf773-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="bf773-110">어떤 업그레이드 방법을 선택하든 온라인에 이미 비즈니스용 Skype 있는 사용자의 경우 [TeamsUpgradePolicy를 사용하여 TeamsOnly로의](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)전환을 관리합니다. 이는 사용자의 공존 모드를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="bf773-111">에 있는 프레미스 계정이 있는 비즈니스용 Skype 서버 클라우드로 이동하는 `Move-CsUser` [데도 사용할 수 있습니다.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="bf773-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="bf773-112">각 모드에 대한 자세한 내용은 공존 모드 [를 참조하세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="bf773-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bf773-113">현재 온라인 커넥터를 사용하여 비즈니스용 Skype 서비스를 관리하는 경우 PowerShell 모듈로 이동하여 Teams PowerShell 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="bf773-114">자세한 내용은 비즈니스용 Skype 온라인 커넥터에서 Teams [PowerShell 모듈로](teams-powershell-move-from-sfbo.md) 이동을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf773-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="bf773-115">기본 비즈니스용 Skype 모드를 사용하여 선택 기능 전환을 수행하거나 기본 섬 구성에서 TeamsOnly 모드로 업그레이드하는 경우 TeamsUpgradePolicy는 기본 도구입니다. 다른 정책과 Teams TeamsUpgradePolicy를 사용자에게 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="bf773-116">정책을 테넌트 전체 기본값으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="bf773-117">사용자에 대한 할당은 테넌트 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="bf773-118">관리 콘솔 및 PowerShell에서 Teams 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="bf773-119">TeamsOnly 모드를 제외한 TeamsUpgradePolicy의 모든 모드를 모든 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="bf773-120">반대로 클라우드에 있는 사용자는 TeamsOnly 모드만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="bf773-121">**TeamsOnly** 모드는 사용자가 온라인 온라인에 비즈니스용 Skype 비즈니스용 Skype 경우만 가능하기 때문에 클라우드에 이미 비즈니스용 Skype 사용자에게만 할당할 수 Microsoft 365 전화 시스템 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="bf773-122">또한 **온-프레미스** 배포가 있는 경우 TeamsOnly 모드를 테넌트 전체 기본값으로 할당할 수 비즈니스용 Skype(lyncdiscover DNS 레코드가 있는 경우 다른 위치를 지정하는 것으로 Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf773-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="bf773-123">자세한 내용은 하이브리드 구성을 사용하지 않도록 설정하여 에서만 으로 [마이그레이션을 Teams 참조합니다.](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="bf773-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="bf773-124">온라인 비즈니스용 Skype 계정이 있는 사용자는 온라인에서 Teams Move-CsUser 도구 비즈니스용 Skype 전용 모드로 이동해야 합니다. [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)</span><span class="sxs-lookup"><span data-stu-id="bf773-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="bf773-125">다른 정책과 달리, 여러 정책에서 TeamsUpgradePolicy의 새 인스턴스를 만들 수 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf773-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bf773-126">모든 기존 인스턴스는 서비스에 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="bf773-127">(모드는 정책 인스턴스의 이름이 아닌 TeamsUpgradePolicy 내의 속성입니다.) 일부에서는 그렇지만 모든 경우에서는 정책 인스턴스의 이름이 모드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="bf773-128">특히 TeamsOnly 모드를 사용자에게 할당하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 해당 사용자에게 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="bf773-129">모든 인스턴스 목록을 표시하기 위해 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="bf773-130">온라인 사용자를 TeamsOnly 모드로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="bf773-131">프레미스 비즈니스용 Skype TeamsOnly 모드로 업그레이드하려면 Move-CsUser 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="bf773-132">테넌트의 모든 사용자에 대한 모드를 변경하기 위해 사용자당 명시적 부여(우선 순위)가 있는 사용자를 제외하고는 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="bf773-133">모든 사용자가 비즈니스용 Skype 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="bf773-134">Move-CsUser를 사용하여 이러한 Teams 전용 모드로 개별적으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="bf773-135">클라이언트에서 알림 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="bf773-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="bf773-136">관리자는 다음 다이어그램에 표시된 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공하여 사용자에게 곧 Teams 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="bf773-137">예를 들어 관리자가 사용자 그룹을 TeamsOnly 모드로 업그레이드하기 일주일 전에 관리자는 해당 사용자 그룹에 대한 이러한 알림을 켜야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="bf773-138">이러한 알림은 NotificationSfbUsers=true와 TeamsUpgradePolicy의 인스턴스를 사용하여 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="bf773-139">TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="bf773-140">TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![알림을 보여주는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="bf773-142">사용자가 온라인에 비즈니스용 Skype 경우 사용자와 동일한 모드가 있지만 NotifySfbUsers=true인 정책 인스턴스를 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="bf773-143">사용자가 비즈니스용 Skype 서버 프레미스에 있는 경우, 2015년에는 2019 또는 CU8을 비즈니스용 Skype 서버 2019 또는 CU8을 비즈니스용 Skype 서버 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="bf773-144">프레미스 비즈니스용 Skype 서버 있는 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스의 모드 속성은 존중되지만, NotifySfbUsers 속성은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="bf773-145">알림이 필요한 경우 클라이언트 동작을 제어하려면 TeamsUpgradePolicy의 프레미스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="bf773-146">On-Premises PowerShell 창에서 NotifySfbUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="bf773-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="bf773-147">그런 다음 동일한 On-Premises PowerShell 창을 사용하여 원하는 사용자에게 해당 새 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="bf773-148">모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="bf773-148">Meeting migration</span></span>

<span data-ttu-id="bf773-149">사용자가 TeamsOnly 모드로 마이그레이션되는 경우 기본적으로 구성한 기존 비즈니스용 Skype 모임이 기본적으로 Teams.</span><span class="sxs-lookup"><span data-stu-id="bf773-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="bf773-150">사용자에게 TeamsOnly 모드를 할당할 때 기본 동작을 선택적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="bf773-151">사용자를온-프레미스에서 이동하는 경우 모임을 클라우드로 마이그레이션하여 온라인 사용자 계정으로 작동해야 하지만 -MoveToTeams를 지정하지 않으면 모임을 비즈니스용 Skype 모임으로 마이그레이션되지 않고 Teams.</span><span class="sxs-lookup"><span data-stu-id="bf773-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="bf773-152">테넌트 수준에서 TeamsOnly 모드를 할당하는 경우 모든 사용자에 대해 모임 마이그레이션이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="bf773-153">테넌트 수준에서 TeamsOnly 모드를 할당하고 모임을 마이그레이션하려는 경우 PowerShell을 사용하여 테넌트의 사용자 목록을(예: 필요한 필터와 함께 Get-CsOnlineUser 사용) 각 사용자를 반복하여 Start-CsExMeetingMigration을 사용하여 모임 마이그레이션을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf773-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="bf773-154">자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조합니다.](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="bf773-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="bf773-155">관련 링크</span><span class="sxs-lookup"><span data-stu-id="bf773-155">Related links</span></span>

[<span data-ttu-id="bf773-156">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="bf773-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="bf773-157">비즈니스용 Skype 서버 및 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="bf773-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="bf773-158">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="bf773-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="bf773-159">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="bf773-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="bf773-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="bf773-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="bf773-161">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="bf773-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
