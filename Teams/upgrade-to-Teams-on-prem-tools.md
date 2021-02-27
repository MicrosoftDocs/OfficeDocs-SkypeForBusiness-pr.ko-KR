---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드하기 위한 도구
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 도구
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61dc34d56ebb10dc7319d855bbd0d98184f1e54a
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347849"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="7eb03-103">IT 관리자를 위한 &mdash; Teams로 업그레이드하기 위한 도구</span><span class="sxs-lookup"><span data-stu-id="7eb03-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="7eb03-104">이 문서에서는 Teams로 업그레이드하기 위한 도구를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="7eb03-105">이 문서는 IT 관리자에 대한 업그레이드 개념 및 구현을 설명하는 세 번째 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="7eb03-106">개요</span><span class="sxs-lookup"><span data-stu-id="7eb03-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="7eb03-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="7eb03-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="7eb03-108">**업그레이드를 관리하는 도구(이**   문서)</span><span class="sxs-lookup"><span data-stu-id="7eb03-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="7eb03-109">비즈니스용 Skype가 있는 조직에 대한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7eb03-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="7eb03-110">업그레이드 수행</span><span class="sxs-lookup"><span data-stu-id="7eb03-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="7eb03-111">PSTN(공용 전환 전화 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7eb03-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="7eb03-112">또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="7eb03-113">Teams 및 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="7eb03-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="7eb03-114">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="7eb03-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="7eb03-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="7eb03-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="7eb03-116">업그레이드를 관리하는 도구</span><span class="sxs-lookup"><span data-stu-id="7eb03-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="7eb03-117">선택한 업그레이드 방법 중 비즈니스용 Skype Online이 이미 있는 사용자의 경우 [TeamsUpgradePolicy를 사용하여 TeamsOnly로의](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)전환을 관리합니다. 이는 사용자의 공존 모드를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="7eb03-118">비즈니스용 Skype Server에서 프레미스 계정이 있는 사용자의 경우 클라우드로 이동하는 `Move-CsUser` [데도 사용할 수 있습니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="7eb03-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="7eb03-119">각 모드에 대한 자세한 내용은 공존 모드 [를 참조하세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="7eb03-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7eb03-120">현재 비즈니스용 Skype Online 커넥터를 사용하여 서비스를 관리하는 경우 Teams PowerShell 모듈로 이동하고 기존 PowerShell 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-120">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="7eb03-121">자세한 [내용은 비즈니스용 Skype Online 커넥터에서 Teams PowerShell](teams-powershell-move-from-sfbo.md) 모듈로 이동을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eb03-121">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="7eb03-122">비즈니스용 Skype 모드를 사용하여 선택 기능 전환을 수행하거나 기본 아일랜드 구성에서 TeamsOnly 모드로 업그레이드하는 경우 TeamsUpgradePolicy는 이미 비즈니스용 Skype Online이 있는 사용자를 위한 기본 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-122">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="7eb03-123">Teams의 다른 정책과 마찬가지로 TeamsUpgradePolicy를 사용자에게 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-123">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="7eb03-124">정책을 테넌트 전체 기본값으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-124">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="7eb03-125">사용자에 대한 할당은 테넌트 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-125">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="7eb03-126">Teams 관리 콘솔 및 PowerShell에서 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-126">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="7eb03-127">TeamsOnly 모드를 제외한 TeamsUpgradePolicy의 모든 모드를 비즈니스용 Skype온-프레미스에 있는 사용자에게 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-127">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="7eb03-128">**TeamsOnly 모드는** 비즈니스용 Skype Online에 이미 있는 사용자에게만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-128">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="7eb03-129">비즈니스용 Skype 사용자 및 페더전드뿐만 아니라 Microsoft 365 Phone System 기능과 상호 연동할 수 있기 때문에 사용자가 비즈니스용 Skype Online에 있는 경우만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-129">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="7eb03-130">또한 비즈니스용 Skype 온-프레미스 배포가 있는 경우 **TeamsOnly** 모드를 테넌트 전체 기본값으로 할당할 수 없습니다(Office 365가외의 위치를 지정하는 lyncdiscover DNS 레코드가 있는 경우 감지).</span><span class="sxs-lookup"><span data-stu-id="7eb03-130">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="7eb03-131">비즈니스용 Skype 계정이 있는 사용자는 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 비즈니스용 Skype온-프레미스 도구 Move-CsUser 사용하여 온라인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-131">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="7eb03-132">이러한 사용자는 1 또는 2단계에서 TeamsOnly로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-132">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="7eb03-133">1단계: Move-CsUser에서 -MoveToTeams 스위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-133">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="7eb03-134">이렇게 하려면 비즈니스용 Skype Server 2019 또는 CU8 이상이 있는 비즈니스용 Skype Server 2015가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-134">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="7eb03-135">2단계: Move-CsUser를 실행한 후 TeamsUpgradePolicy를 사용하여 사용자에게 TeamsOnly 모드를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-135">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="7eb03-136">다른 정책과 달리 Microsoft 365 또는 Office 365에서 TeamsUpgradePolicy의 새 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-136">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7eb03-137">모든 기존 인스턴스는 서비스에 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-137">All the existing instances are built into the service.</span></span>  <span data-ttu-id="7eb03-138">(모드는 정책 인스턴스의 이름이 아닌 TeamsUpgradePolicy 내의 속성입니다.) 일부에서는 그렇지만 모든 경우에서는 정책 인스턴스의 이름이 모드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-138">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="7eb03-139">특히 TeamsOnly 모드를 사용자에게 할당하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 해당 사용자에게 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-139">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="7eb03-140">모든 인스턴스 목록을 표시하기 위해 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-140">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="7eb03-141">온라인 사용자를 TeamsOnly 모드로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-141">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="7eb03-142">비즈니스용 Skype 사용자를 TeamsOnly 모드로 업그레이드하려면 Move-CsUser 도구세트에서 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-142">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="7eb03-143">테넌트의 모든 사용자에 대한 모드를 변경하기 위해 사용자당 명시적 부여(우선 순위)가 있는 사용자를 제외하고는 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-143">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="7eb03-144">비즈니스용 Skype 계정이 있는 사용자가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-144">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="7eb03-145">Move-CsUser를 사용하여 이러한 사용자를 클라우드로 개별적으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-145">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="7eb03-146">비즈니스용 Skype 클라이언트에서 알림 사용</span><span class="sxs-lookup"><span data-stu-id="7eb03-146">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="7eb03-147">관리자는 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공하여 사용자에게 다음 다이어그램과 같이 곧 Teams로 업그레이드될 것 을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-147">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="7eb03-148">예를 들어 관리자가 사용자 그룹을 TeamsOnly 모드로 업그레이드하기 일주일 전에 관리자는 해당 사용자 그룹에 대한 이러한 알림을 켜야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-148">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="7eb03-149">이러한 알림은 NotificationSfbUsers=true와 TeamsUpgradePolicy의 인스턴스를 사용하여 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-149">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="7eb03-150">TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-150">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="7eb03-151">TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-151">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![알림을 보여주는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="7eb03-153">사용자가 비즈니스용 Skype Online에 있는 경우 사용자와 동일한 모드가 있지만 NotifySfbUsers=true인 정책 인스턴스를 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-153">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="7eb03-154">사용자가 비즈니스용 Skype 서버 온라인 프레미스에 있는 경우, 비즈니스용 Skype 서버 2019 또는 비즈니스용 Skype Server 2015용 CU8을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-154">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="7eb03-155">비즈니스용 Skype Server온-프레미스에 있는 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스의 모드 속성은 존중되지만, NotifySfbUsers 속성은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-155">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="7eb03-156">알림이 필요한 경우 클라이언트 동작을 제어하려면 TeamsUpgradePolicy의 프레미스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-156">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="7eb03-157">On-Premises PowerShell 창에서 NotifySfbUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="7eb03-157">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="7eb03-158">그런 다음 동일한 On-Premises PowerShell 창을 사용하여 원하는 사용자에게 해당 새 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-158">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="7eb03-159">모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7eb03-159">Meeting migration</span></span>

<span data-ttu-id="7eb03-160">사용자가 TeamsOnly 모드로 마이그레이션되는 경우 기본적으로 사용자가 구성한 기존 비즈니스용 Skype 모임이 Teams로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-160">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="7eb03-161">사용자에게 TeamsOnly 모드를 할당할 때 기본 동작을 선택적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-161">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="7eb03-162">사용자를온-프레미스에서 이동하는 경우 모임을 클라우드로 마이그레이션하여 온라인 사용자 계정으로 작동해야 하지만 -MoveToTeams를 지정하지 않으면 모임이 Teams로 변환되지 않고 비즈니스용 Skype 모임으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-162">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="7eb03-163">테넌트 수준에서 TeamsOnly 모드를 할당하는 경우 모든 사용자에 대해 모임 마이그레이션이 트리거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-163">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="7eb03-164">테넌트 수준에서 TeamsOnly 모드를 할당하고 모임을 마이그레이션하려는 경우 PowerShell을 사용하여 테넌트의 사용자 목록을(예: 필요한 필터와 함께 Get-CsOnlineUser 사용) 각 사용자를 반복하여 Start-CsExMeetingMigration을 사용하여 모임 마이그레이션을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eb03-164">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="7eb03-165">자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조합니다.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="7eb03-165">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="7eb03-166">관련 링크</span><span class="sxs-lookup"><span data-stu-id="7eb03-166">Related links</span></span>

[<span data-ttu-id="7eb03-167">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="7eb03-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="7eb03-168">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="7eb03-168">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="7eb03-169">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="7eb03-169">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="7eb03-170">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="7eb03-170">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="7eb03-171">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="7eb03-171">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="7eb03-172">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="7eb03-172">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

