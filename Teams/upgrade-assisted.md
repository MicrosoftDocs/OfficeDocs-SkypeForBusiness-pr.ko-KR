---
title: 보조 업그레이드 | Skype Business Online에서 Teams 업그레이드로
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 비즈니스용 Skype Online에서 Teams로의 보조 업그레이드 개요
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995203"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="b6979-103">비즈니스용 Skype Online에서 Microsoft Teams로 업그레이드 지원</span><span class="sxs-lookup"><span data-stu-id="b6979-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="b6979-104">Microsoft는 조직이 2021년 7월 31일 서비스를 사용 중지할 때 비즈니스용 Skype Online에서 성공적으로 전환할 수 있도록 Teams에 대한 지원 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="b6979-105">보조 업그레이드는 필요한 기술 작업 수를 줄이고 조직 준비, 사용자 인식 및 Teams 교육에 더 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-105">Assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="b6979-106">업그레이드 전에 업그레이드 지침을 [검토하는](https://aka.ms/SkypeToTeams) 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="b6979-107">업그레이드 지침에는 비즈니스용 Skype Online에서 Teams로 업그레이드를 완료하기 위한 권장 활동 및 유용한 리소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="b6979-108">이 지침은 업그레이드의 모든 측면을 관리하거나 보조 프로세스를 사용하는 등 Teams로 업그레이드를 계획하는 모든 조직에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="b6979-109">Teams로 보조 업그레이드를 예약하는 경우 예약된 업그레이드 날짜 전에 비즈니스용 Skype Online에서 자체 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="b6979-110">Teams로 수동으로 업그레이드하는 방법에 대한 자세한 내용은 업그레이드 지침 [을 참조하세요.](https://aka.ms/SkypeToTeams)</span><span class="sxs-lookup"><span data-stu-id="b6979-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="b6979-111">비즈니스용 Skype Server의 사내 배포에는 보조 업그레이드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-111">Assisted upgrade is not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="b6979-112">예약된 고객에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="b6979-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="b6979-113">Teams로의 보조 업그레이드가 예정된 비즈니스용 Skype Online 고객은 일련의 업그레이드 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="b6979-114">이러한 알림은 예약된 업그레이드 날짜 90일 전에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="b6979-115">이러한 알림은 Microsoft  365 메시지 센터의 변경 계획 게시물, Teams 관리 센터의 대시보드 알림 업그레이드, 앱 내 플래그를 최종 사용자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="b6979-116">업그레이드 알림에는 보조 업그레이드의 예약된 날짜가 포함되어 있으며, 리소스 및 교육을 업그레이드하여 Teams 채택 및 사용에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="b6979-117">보조 업그레이드 환경</span><span class="sxs-lookup"><span data-stu-id="b6979-117">The assisted upgrade experience</span></span>

<span data-ttu-id="b6979-118">보조 업그레이드는 위에서 언급한 일정 알림에서 테넌트별 날짜를 공유하여 2021년 8월에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="b6979-119">업그레이드 기간은 사용자 볼륨 및 배포의 특성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-119">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="b6979-120">그러나 대부분의 경우 테넌트 내의 사용자는 업그레이드가 시작된 후 24시간 이내에 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-120">However, in most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="b6979-121">이 기간 동안 최종 사용자는 비즈니스용 Skype Online 기능에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-121">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="b6979-122">업그레이드가 완료된 후 비즈니스용 Skype Online에서 사용자가 로그인하면 메시징, 모임 및 통화에 Teams를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-122">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="b6979-123">업그레이드 후 환경</span><span class="sxs-lookup"><span data-stu-id="b6979-123">The post-upgrade experience</span></span>

<span data-ttu-id="b6979-124">보조 업그레이드가 완료되면 업그레이드된  사용자에 대한 공존 모드가 Teams 전용으로 설정되어 Microsoft에서 다른 공존 모드로만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-124">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only and can only be changed to a different coexistence mode by Microsoft.</span></span> <span data-ttu-id="b6979-125">업그레이드하기 전에 [Teams Only 모드 고려](teams-only-mode-considerations.md) 사항을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-125">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="b6979-126">아래 표에서는 Teams Only 사용자 경험에 대한 높은 수준의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-126">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="b6979-127">**채팅 및 통화**</span><span class="sxs-lookup"><span data-stu-id="b6979-127">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="b6979-128">모든 통화 및 채팅이 Teams에서 시작 및 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-128">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="b6979-129">사용자는 비즈니스용 Skype 사용자와 통신(채팅/통화)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-129">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="b6979-130">조직에서는 Teams 사용자가 외부 액세스 권한을 관리하여 Skype 소비자 서비스 사용자와 통신할 수 있도록 [설정할 수 있습니다.](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="b6979-130">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="b6979-131">비즈니스용 Skype Online에 로그인을 시도하는 팀 사용자가 Teams로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-131">Teams users who attempt to sign in to Skype for Business Online will be redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="b6979-132">**모임**</span><span class="sxs-lookup"><span data-stu-id="b6979-132">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="b6979-133">사용자가 Teams에서 모든 새 모임 예약(플러그 인 대체)</span><span class="sxs-lookup"><span data-stu-id="b6979-133">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="b6979-134">**마이그레이션된 데이터**</span><span class="sxs-lookup"><span data-stu-id="b6979-134">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="b6979-135">페더리드를 포함한 비즈니스용 Skype Online의 기존 연락처(메일 목록 없음)</span><span class="sxs-lookup"><span data-stu-id="b6979-135">Existing contacts from Skype for Business Online including federated (but no distribution lists</span></span>
        - <span data-ttu-id="b6979-136">기존 비즈니스용 Skype Online 모임이 Teams 모임으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6979-136">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
    :::column-end:::
:::row-end:::

## <a name="related-content"></a><span data-ttu-id="b6979-137">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b6979-137">Related content</span></span>

- [<span data-ttu-id="b6979-138">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="b6979-138">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="b6979-139">비즈니스용 Skype Online 단종</span><span class="sxs-lookup"><span data-stu-id="b6979-139">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="b6979-140">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="b6979-140">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="b6979-141">Teams 전용 모드 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b6979-141">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
