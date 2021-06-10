---
title: 빠른 시작 가이드 - 통화 계획 구성
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 실행 중인 사용자 집합을 Microsoft Teams 호출 계획을 구성하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101184"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="6ec6a-103">빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="6ec6a-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="6ec6a-104">이 가이드는 사용자 집합을 설정하고 실행하는 데 도움이 되어 사용자가 전화 요금제에서 호출 계획을 탐색할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="6ec6a-105">2017년 12월 12일, Teams: [Intelligent Communications는](https://aka.ms/ipyqus) 다음 단계를 Teams</span><span class="sxs-lookup"><span data-stu-id="6ec6a-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="6ec6a-106">이 빠른 시작 가이드와 함께 성공적인 [롤아웃을](calling-plan-landing-page.md) 계획하고 구동하기 위해 전화 시스템 [및 FastTrack을](https://aka.ms/cloudvoice) 통해 이 가이드를 읽어보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="6ec6a-107">이제 PSTN(공용 Microsoft 365 Office 365)을 통해 전화 통화 요금제와 비즈니스용 Skype 기능을 추가하여 Teams 전화 통화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![연락처 페이지를 보여주는 화면 Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="6ec6a-109">통화 탭을 사용할 수 있도록  설정하기 위한 Teams</span><span class="sxs-lookup"><span data-stu-id="6ec6a-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="6ec6a-110">사용자가 Teams  통화 탭을 사용하도록 설정하려면 사용자가 1:1 Teams 1:1 호출을 지원하는 Teams 클라이언트를 사용하여 1:1 호출을 사용하도록 설정해야 Teams.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="6ec6a-111">에서 1:1 호출을 관리하는 방법을 알아보 Teams [Set-CsTeamsCallingPolicy 를 읽어보아야 합니다.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6ec6a-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="6ec6a-112">호출을 지원하는 클라이언트를 알아보시고 에 대한 제한 및 사양을 [Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6ec6a-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6ec6a-113">현재 사용자가 PSTN 호출에 대해 사용하도록 설정되어 있지 않으면 통화 탭에서 Voicemail을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="6ec6a-114">다이얼 패드를 사용할 수 있도록  설정하기 위한 Teams</span><span class="sxs-lookup"><span data-stu-id="6ec6a-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="6ec6a-115">전화 걸기 패드 탭을 Teams 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 사용자 전화 시스템 및 통화 요금제에 대해 사용자를 프로비전해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="6ec6a-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="6ec6a-116">통화 계획을 설정하는 방법에 대해 알아보고자 하는 경우 통화 계획 설정 [을 읽어보아야 합니다.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ec6a-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="6ec6a-117">또한 사용자만 Teams 경우 통화 정책에서 "개인 호출 허용"을 사용하도록 Teams 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="6ec6a-118">자세한 Teams 관리 [센터로](./manage-teams-skypeforbusiness-admin-center.md) 전환하는 동안 Microsoft Teams 관리 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="6ec6a-119">직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="6ec6a-120">직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성 을 읽어보아야 합니다.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6ec6a-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="6ec6a-121">TeamsUpgradePolicy를 사용하여 토지 호출 위치를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="6ec6a-122">들어오는 호출(및 채팅)이 Teams 비즈니스용 Skype 여부를 제어하기 위해 관리자는 관리자 센터에서 Microsoft Teams 또는 원격 Windows PowerShell [](https://aka.ms/teamsadmincenter) cmdlet을 사용하여 TeamsUpgradePolicy를 [](/powershell/module/skype) 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="6ec6a-123">TeamsUpgradePolicy의 기본 구성은 기존 비즈니스 워크플로가 배포하는 동안 중단되지 않도록 Teams 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="6ec6a-124">기본적으로 사용자에 대한 VoIP, PSTN Teams 및 페더링된 호출은 정책을 업데이트할 때까지 비즈니스용 Skype 로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="6ec6a-125">받는 사람이 섬 모드인 경우:</span><span class="sxs-lookup"><span data-stu-id="6ec6a-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="6ec6a-126">수신 VOIP 호출은 비즈니스용 Skype 클라이언트에 항상 비즈니스용 Skype 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="6ec6a-127">보낸 사람 및 수신기가 동일한 Teams 에 Teams 수신 VOIP 호출</span><span class="sxs-lookup"><span data-stu-id="6ec6a-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="6ec6a-128">들어오는 페더리드 VOIP(클라이언트가 시작된 대상에 관계 없이) 및 PSTN 호출은 항상 받는 사람의 클라이언트에 비즈니스용 Skype 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="6ec6a-129">들어오는 VOIP 및 PSTN 호출이 항상 사용자의 클라이언트에 Teams 있도록 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="6ec6a-130">공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 사용자와 함께 Teams 조직에 대한 마이그레이션 [및](./migration-interop-guidance-for-teams-with-skype.md) 상호운용성 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec6a-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="6ec6a-131">**참고 사항**</span><span class="sxs-lookup"><span data-stu-id="6ec6a-131">**NOTES**</span></span>
 - <span data-ttu-id="6ec6a-132">비즈니스용 Skype 사용자가 TeamsOnly 모드인 경우에도 IP 휴대폰에서 통화가 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="6ec6a-133">전화 시스템 온라인과 함께 사용하기 위해 비즈니스용 Skype 및 호출 계획 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값)에는 호출 탭이 Teams 설정되고 관리자가 관리 작업을 수행하지 않고도 Teams 아웃바운드 PSTN 호출을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="6ec6a-134">들어오는 모든 VOIP 및 PSTN 호출을 수신하도록 사용자를 구성하는 Teams</span><span class="sxs-lookup"><span data-stu-id="6ec6a-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="6ec6a-135">사용자가 수신되는 모든 VOIP 및 PSTN 호출을 Teams 관리 센터에서 TeamsOnly로 설정하거나 Microsoft Teams 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 다음과 같이 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec6a-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="6ec6a-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ec6a-136">See also</span></span>
[<span data-ttu-id="6ec6a-137">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="6ec6a-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="6ec6a-138">조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec6a-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="6ec6a-139">통화 플랜을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="6ec6a-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="6ec6a-140">비즈니스용 Skype PowerShell cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="6ec6a-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)