---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940675"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="baed2-103">IT 관리자를 위한 팀으로 업그레이드 하기 위한 도구 &mdash;</span><span class="sxs-lookup"><span data-stu-id="baed2-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="baed2-104">이 문서에서는 팀으로 업그레이드 하기 위한 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="baed2-105">이 문서는 IT 관리자의 업그레이드 개념 및 구현에 대해 설명 하는 몇 가지 항목 중 세 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="baed2-106">개요</span><span class="sxs-lookup"><span data-stu-id="baed2-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="baed2-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="baed2-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="baed2-108">**업그레이드 관리 도구**   (이 문서)</span><span class="sxs-lookup"><span data-stu-id="baed2-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="baed2-109">비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="baed2-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="baed2-110">업그레이드 수행</span><span class="sxs-lookup"><span data-stu-id="baed2-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="baed2-111">PSTN (공개 통신 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="baed2-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="baed2-112">또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="baed2-113">팀과 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="baed2-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="baed2-114">공존 모드-참조</span><span class="sxs-lookup"><span data-stu-id="baed2-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="baed2-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="baed2-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="baed2-116">업그레이드 관리 도구</span><span class="sxs-lookup"><span data-stu-id="baed2-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="baed2-117">어떤 업그레이드 방법을 선택 하 든 사용자의 공존 모드를 제어 하는 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)을 사용 하는 경우에만 teamsonly로 전환을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="baed2-118">각 모드에 대 한 자세한 내용은 [공존 모드](migration-interop-guidance-for-teams-with-skype.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="baed2-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="baed2-119">Skype for Business 모드를 사용 하 여 선택 기능 전환을 수행 하 든, 기본 군도 구성에서 팀 전용 모드로만 업그레이드 하는 경우 TeamsUpgradePolicy는 기본 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="baed2-120">팀의 다른 정책과 마찬가지로 TeamsUpgradePolicy를 사용자에 게 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="baed2-121">또한 정책을 테 넌 트 차원의 기본값으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="baed2-122">사용자에 게 할당 하는 모든 작업은 테 넌 트 기본 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="baed2-123">팀 관리 콘솔과 PowerShell에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="baed2-124">비즈니스용 skype **online에서 이미 사용 중인 사용자 에게만 팀 전용 모드를 배정할 수 있다는 점을 제외**하 고 사용자에 게 TeamsUpgradePolicy의 모드를 비즈니스용 skype online 또는 온-프레미스로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="baed2-125">이는 사용자가 비즈니스용 Skype Online에 있는 경우에만 비즈니스용 Skype 사용자 및 페더레이션이 있는 interop와 Microsoft 365 전화 시스템 기능을 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="baed2-126">비즈니스용 skype 계정을 사용 하는 사용자는 비즈니스용 skype 온-프레미스 도구 모음에서 이동-CsUser를 사용 하 여 온라인 (비즈니스용 Skype Online 또는 팀에 직접)으로 [이동 해야 합니다](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) .</span><span class="sxs-lookup"><span data-stu-id="baed2-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="baed2-127">이러한 사용자는 1 개 또는 2 개 단계 에서만 TeamsOnly로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="baed2-128">1 단계: CsUser 이동에서-MoveToTeams 스위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="baed2-129">이를 위해서는 비즈니스용 Skype Server 2019 또는 CU8 또는 이후 버전의 비즈니스용 Skype Server 2015이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="baed2-130">2 단계: CsUser Move를 실행 한 후 TeamsUpgradePolicy를 사용 하 여 사용자에 게 TeamsOnly 모드를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="baed2-131">다른 정책과는 달리 Microsoft 365 또는 Office 365에서 새 TeamsUpgradePolicy 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="baed2-132">모든 기존 인스턴스가 서비스에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="baed2-133">(Mode는 정책 인스턴스의 이름이 아니라 TeamsUpgradePolicy 내에 있는 속성입니다.) 일부 경우에는 그렇지 않고 정책 인스턴스의 이름은 mode와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="baed2-134">특히, 팀 전용 모드를 사용자에 게 할당 하는 경우 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스가 해당 사용자에 게 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="baed2-135">다음 명령을 실행 하 여 모든 인스턴스 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="baed2-136">온라인 사용자를 팀 전용 모드로 업그레이드 하려면 "UpgradeToTeams" 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="baed2-137">온-프레미스 비즈니스용 Skype 사용자를 팀 전용 모드로 업그레이드 하려면 온-프레미스 도구 모음에서-CsUser Move 사용자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="baed2-138">특정 사용자별 권한 부여 (우선 순위)가 있는 경우를 제외 하 고 테 넌 트에서 모든 사용자에 대 한 모드를 변경 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="baed2-139">비즈니스용 Skype 계정을 보유 하 고 있는 사용자가 있는 경우, 온-프레미스 Skype 계정으로 모든 사용자에 게 다른 모드를 명시적으로 할당 하지 않는 한, 테 넌 트 수준에서 TeamsOnly 모드를 할당 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="baed2-140">비즈니스용 Skype 클라이언트에서 알림 사용</span><span class="sxs-lookup"><span data-stu-id="baed2-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="baed2-141">관리자는 다음 다이어그램에 표시 된 것 처럼 사용자에 게 곧 팀으로 업그레이드할 것을 알리기 위해 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="baed2-142">예를 들어 관리자가 팀 전용 모드로 사용자 그룹을 업그레이드 하기 전에 관리자는 해당 사용자 그룹에 대해 이러한 알림을 설정 하 려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="baed2-143">이러한 알림은 NotifySfbUsers = true 인 TeamsUpgradePolicy 인스턴스를 사용 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="baed2-144">TeamsOnly 이외의 모든 모드에서는 실제로 두 개의 NotifySfbUsers 값에 해당 하는 mode 당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="baed2-145">TeamsOnly 이외의 모든 모드에서는 실제로 두 개의 NotifySfbUsers 값에 해당 하는 mode 당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![알림을 표시 하는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="baed2-147">사용자가 비즈니스용 Skype Online에서 사용 되는 경우 사용자와 동일한 모드의 정책 인스턴스를 할당 하 되 NotifySfbUsers = true를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="baed2-148">사용자가 비즈니스용 Skype Server 온-프레미스에 있는 경우 온-프레미스 도구 모음을 사용 해야 하며 비즈니스용 skype server 2019 또는 CU8 for Business Server 2015의 경우이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="baed2-149">비즈니스용 Skype Server 온-프레미스에 속한 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스에서 mode 속성이 적용 되지만 NotifySfbUsers 속성은 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="baed2-150">알림을 원하는 경우 클라이언트 동작을 제어 하려면 온-프레미스 인스턴스를 TeamsUpgradePolicy으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="baed2-151">온-프레미스 PowerShell 창에서 NotifySfbUsers = true를 사용 하 여 TeamsUpgradePolicy의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="baed2-152">그런 다음, 온-프레미스 PowerShell 창을 사용 하 여 원하는 사용자에 게 새 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="baed2-153">모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="baed2-153">Meeting migration</span></span>

<span data-ttu-id="baed2-154">사용자가 팀 전용 모드로 마이그레이션될 때 기본적으로 자신이 구성한 비즈니스용 Skype 모임이 팀으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="baed2-155">사용자에 게 팀 전용 모드를 할당할 때 선택적으로 기본 동작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="baed2-156">온-프레미스에서 사용자를 이동 하는 경우 온라인 사용자 계정에 대 한 모임을 작동 하도록 클라우드로 마이그레이션해야 하지만,-MoveToTeams를 지정 하지 않으면 모임이 팀으로 변환 되지 않고 비즈니스용 Skype 모임으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="baed2-157">테 넌 트 수준에서 TeamsOnly 모드를 할당할 때 모임 마이그레이션은 사용자에 대해 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="baed2-158">테 넌 트 수준에서 TeamsOnly 모드를 할당 하 고 모임을 마이그레이션하려면 PowerShell을 사용 하 여 테 넌 트의 사용자 목록을 가져올 수 있습니다 (예: 필요한 필터와 함께 CsOnlineUser 사용). 그런 다음 이러한 사용자 각각을 순환 하 여 Start-CsExMeetingMigration를 사용 하 여 모임 마이그레이션을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="baed2-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="baed2-159">자세한 내용은 [MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="baed2-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="baed2-160">관련 링크</span><span class="sxs-lookup"><span data-stu-id="baed2-160">Related links</span></span>

[<span data-ttu-id="baed2-161">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="baed2-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="baed2-162">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="baed2-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="baed2-163">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="baed2-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="baed2-164">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="baed2-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="baed2-165">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="baed2-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="baed2-166">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="baed2-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

