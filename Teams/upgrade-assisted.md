---
title: 보조 업그레이드 | Skype 업그레이드할 비즈니스 Teams 온라인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 온라인에서 온라인으로의 비즈니스용 Skype 업그레이드 개요 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e445fd6c5d26a64005ff1c285d8e9d843ca0211
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656061"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="520ce-103">온라인에서 비즈니스용 Skype 업그레이드를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="520ce-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="520ce-104">Microsoft는 서비스가 2021년 7월 31일 Teams 조직이 온라인에서 성공적인 전환을 비즈니스용 Skype 수 있도록 지원되는 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="520ce-105">조직이 비즈니스용 Skype 온라인에서  업그레이드하거나 비즈니스용 Skype(비즈니스용 Skype 온라인 및 비즈니스용 Skype 서버) 환경에서 온라인을 업그레이드하는지 여부에 따라 보조 업그레이드는 필요한 기술 작업 수를 줄이고 조직 준비, 사용자 인식 및 Teams 집중할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="520ce-105">Whether your organization is upgrading from a *Skype for Business Online* or *Skype for Business Online with hybrid* (users in both Skype for Business Online **and** Skype for Business Server) environment, assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="520ce-106">업그레이드 전에 업그레이드 지침을 [검토하는](https://aka.ms/SkypeToTeams) 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="520ce-107">업그레이드 지침에는 온라인에서 온라인으로 업그레이드를 완료하기 위한 권장 활동 및 비즈니스용 Skype 유용한 리소스가 Teams.</span><span class="sxs-lookup"><span data-stu-id="520ce-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="520ce-108">이 지침은 업그레이드의 모든 측면을 관리하거나 보조 프로세스를 Teams 조직에서 업그레이드를 계획하는 모든 조직에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="520ce-109">지원 업그레이드를 예약한 경우 Teams 업그레이드 날짜 전에 온라인에서 비즈니스용 Skype 자체 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="520ce-110">수동으로 업그레이드하는 방법에 대한 자세한 내용은 업그레이드 Teams [을 참조하세요.](https://aka.ms/SkypeToTeams)</span><span class="sxs-lookup"><span data-stu-id="520ce-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="520ce-111">지원 업그레이드는 프레미스에서 배포할 수 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="520ce-111">Assisted upgrades are not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="520ce-112">예약된 고객에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="520ce-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="520ce-113">비즈니스용 Skype 지원된 업그레이드를 예약한 온라인 Teams 일련의 업그레이드 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="520ce-114">이러한 알림은 예약된 업그레이드 날짜 90일 전에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="520ce-115">이러한 알림은 메시지  센터의 변경 계획 Microsoft 365 관리 센터에서 대시보드 알림을 업그레이드하고, 최종 사용자에게 Teams 앱 내 플래그로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="520ce-116">업그레이드 알림에는 보조 업그레이드의 예약된 날짜가 포함되어 있으며, 리소스 및 교육을 업그레이드하여 업그레이드를 통해 업그레이드를 지원하고 사용 현황을 Teams.</span><span class="sxs-lookup"><span data-stu-id="520ce-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="520ce-117">보조 업그레이드 환경</span><span class="sxs-lookup"><span data-stu-id="520ce-117">The assisted upgrade experience</span></span>

<span data-ttu-id="520ce-118">보조 업그레이드는 위에서 언급한 일정 알림에서 테넌트별 날짜를 공유하여 2021년 8월에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="520ce-119">지원되는 업그레이드 환경은 하이브리드 환경이 있는 비즈니스용 Skype 온라인 전용 또는 비즈니스용 Skype 여부에 따라 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-119">Your assisted upgrade experience will differ slightly depending on whether you have a Skype for Business Online-only or a Skype for Business Online with hybrid environment:</span></span>

- <span data-ttu-id="520ce-120">**비즈니스용 Skype 온라인 전용** 보조 업그레이드 프로세스는 조직에 `TeamsUpgradeOverridePolicy` 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-120">**Skype for Business Online-only** The assisted upgrade process will apply the `TeamsUpgradeOverridePolicy` policy to your organization.</span></span> <span data-ttu-id="520ce-121">이 정책이 적용된 경우 모든 비즈니스용 Skype 모든 온라인 사용자가 Teams 모드로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-121">When this policy is applied, all your Skype for Business Online users will be placed in Teams Only mode.</span></span>
- <span data-ttu-id="520ce-122">**비즈니스용 Skype 있는 온라인** 하이브리드 환경에는 다음 범주 중 하나에 속하는 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-122">**Skype for Business Online with hybrid** Hybrid environments may have users that fall into one of the following categories:</span></span>

  - <span data-ttu-id="520ce-123">프레미스에 홈이 있는 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="520ce-123">On-premises users homed on Skype for Business Server</span></span>
  - <span data-ttu-id="520ce-124">비즈니스용 Skype 전용 모드에 있는 Teams 사용자</span><span class="sxs-lookup"><span data-stu-id="520ce-124">Skype for Business Online users that are in Teams Only mode</span></span>
  - <span data-ttu-id="520ce-125">비즈니스용 Skype 전용 모드가  아닌 Teams 사용자</span><span class="sxs-lookup"><span data-stu-id="520ce-125">Skype for Business Online users that are **not** in Teams Only mode</span></span>

  <span data-ttu-id="520ce-126">위에 나열된 각 범주에 사용자가 혼합되어 있는 경우 보조 업그레이드 프로세스는 해당 비즈니스용 Skype 없는 경우 Teams 전용 모드로만 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-126">If you have a mixture of users in each of the categories listed above, the assisted upgrade process will only switch Skype for Business Online users to Teams Only mode if they're not already in that mode.</span></span> <span data-ttu-id="520ce-127">프레미스 비즈니스용 Skype 업그레이드 프로세스에 영향을주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-127">On-premises Skype for Business users won't be impacted by the assisted upgrade process.</span></span>

> [!NOTE]
> <span data-ttu-id="520ce-128">보조 업그레이드가 2021년 7월 31일 이후 날짜로 예약된 경우 걱정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="520ce-128">Don't worry if your assisted upgrade is scheduled for a date after July 31, 2021.</span></span> <span data-ttu-id="520ce-129">조직은 업그레이드가 완료될 때까지 비즈니스용 Skype 온라인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-129">Your organization will be able to use Skype for Business Online until your upgrade is complete.</span></span>

<span data-ttu-id="520ce-130">업그레이드 기간은 사용자 볼륨 및 배포의 특성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-130">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="520ce-131">대부분의 경우 테넌트 내의 사용자는 업그레이드가 시작된 후 24시간 이내에 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-131">In most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="520ce-132">이 기간 동안 최종 사용자는 여전히 온라인 비즈니스용 Skype 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-132">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="520ce-133">업그레이드가 완료되면 사용자가 온라인에서 비즈니스용 Skype, 메시지, 모임 및 통화에 Teams 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-133">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="520ce-134">업그레이드 후 환경</span><span class="sxs-lookup"><span data-stu-id="520ce-134">The post-upgrade experience</span></span>

<span data-ttu-id="520ce-135">보조 업그레이드가 완료되면 업그레이드된  사용자에 대한 공존 모드가 Teams만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-135">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only.</span></span> <span data-ttu-id="520ce-136">업그레이드하기 전에 Teams [모드](teams-only-mode-considerations.md) 고려 사항을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-136">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="520ce-137">아래 표에서는 사용자 환경만의 Teams 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-137">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="520ce-138">**채팅 및 통화**</span><span class="sxs-lookup"><span data-stu-id="520ce-138">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="520ce-139">모든 통화 및 채팅이 시작되어 수신됩니다Teams</span><span class="sxs-lookup"><span data-stu-id="520ce-139">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="520ce-140">사용자는 모든 사용자와 통신(채팅/비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-140">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="520ce-141">조직에서는 외부 Teams 관리하여 Skype 사용자와 통신할 [수 있습니다.](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="520ce-141">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="520ce-142">Teams 온라인에 로그인하려고 시도하는 비즈니스용 Skype 사용자로 리디렉션됩니다Teams</span><span class="sxs-lookup"><span data-stu-id="520ce-142">Teams users who attempt to sign in to Skype for Business Online are redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="520ce-143">**모임**</span><span class="sxs-lookup"><span data-stu-id="520ce-143">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="520ce-144">사용자가 모든 새 모임을 Teams(플러그 인 대체)</span><span class="sxs-lookup"><span data-stu-id="520ce-144">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="520ce-145">**마이그레이션된 데이터**</span><span class="sxs-lookup"><span data-stu-id="520ce-145">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="520ce-146">페더리드를 포함하여 비즈니스용 Skype Online의 기존 연락처(메일 목록 없음)</span><span class="sxs-lookup"><span data-stu-id="520ce-146">Existing contacts from Skype for Business Online including federated (but no distribution lists)</span></span>
        - <span data-ttu-id="520ce-147">사용자가 처음으로 로그인할 때 Teams 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-147">Contacts are migrated when users log into Teams for the first time.</span></span>
            > [!IMPORTANT]
            ><span data-ttu-id="520ce-148">업그레이드가 완료된 후 90일 이내에 연락처를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-148">Contacts must be migrated within 90 days of the completion of your upgrade.</span></span>
        - <span data-ttu-id="520ce-149">기존 비즈니스용 Skype 온라인 모임이 Teams 모임으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-149">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
            > [!IMPORTANT]
            > <span data-ttu-id="520ce-150">순수 온라인 비즈니스용 Skype 고객은 MMS(모임 마이그레이션 서비스)를 사용하여 기존 온라인 모임을 비즈니스용 Skype 모임으로 마이그레이션해야 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-150">Customers with pure Skype for Business Online configurations need to use the Meeting Migration Service (MMS) to migrate existing Skype for Business Online meetings to Teams meetings.</span></span> <span data-ttu-id="520ce-151">지원된 업그레이드 날짜 이전에 MMS를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-151">We recommend using MMS prior to the assisted upgrade date.</span></span> <span data-ttu-id="520ce-152">MMS에 대한 자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조하세요.](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="520ce-152">For more information about MMS, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="520ce-153">업그레이드가 완료되면 하이브리드 배포가 있는 조직은 사용자를 프레미스에서 Teams 또는 Teams 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="520ce-153">After your upgrade is complete, organizations with hybrid deployments may move users from on-premises to Teams or moved from Teams to on-premises.</span></span>  

## <a name="related-content"></a><span data-ttu-id="520ce-154">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="520ce-154">Related content</span></span>

- [<span data-ttu-id="520ce-155">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="520ce-155">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="520ce-156">비즈니스용 Skype Online 단종</span><span class="sxs-lookup"><span data-stu-id="520ce-156">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="520ce-157">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="520ce-157">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="520ce-158">Teams 모드 고려 사항만</span><span class="sxs-lookup"><span data-stu-id="520ce-158">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
