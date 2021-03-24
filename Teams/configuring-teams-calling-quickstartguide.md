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
description: Microsoft Teams에서 호출 계획을 구성하기 위한 빠른 시작 가이드를 통해 사용자 집합을 실행하고 시작할 수 있습니다.
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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="0602b-103">빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="0602b-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="0602b-104">이 가이드는 Teams에서 통화 계획을 탐색할 수 있도록 사용자 집합을 설정하고 실행하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="0602b-105">2017년 12월 12일, Teams의 통화 계획 발표: [Intelligent Communications는 Teams에서](https://aka.ms/ipyqus) 통화를 통해 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="0602b-106">이 빠른 시작 가이드와 병행하여 통화 [](calling-plan-landing-page.md) 계획 및 [FastTrack을](https://aka.ms/cloudvoice) 통해 전화 시스템을 읽고 성공적인 롤아웃을 계획하고 구동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="0602b-107">이제 비즈니스용 Skype에서 사용하는 Microsoft 365 및 Office 365 기능인 통화 계획을 추가하여 이제 Teams를 사용하여 PSTN(공용 전화 네트워크)을 통해 전화선 및 휴대폰으로 전화 통화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="0602b-109">Teams에서 통화 탭을 사용하도록  설정하기 위한 전제</span><span class="sxs-lookup"><span data-stu-id="0602b-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="0602b-110">Teams에서  통화 탭을 사용하도록 설정하려면 Teams에서 1:1 호출을 사용하도록 설정하고 1:1 Teams 호출을 지원하는 Teams 클라이언트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="0602b-111">Teams에서 1:1 통화를 관리하는 방법에 대해 알아보고자 하는 경우 [Set-CsTeamsCallingPolicy 를 읽어보아야 합니다.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0602b-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="0602b-112">호출을 지원하는 클라이언트를 알아보고자 하는 경우 Microsoft Teams의 제한 및 [사양을 읽어보아야 합니다.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0602b-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0602b-113">현재 사용자가 PSTN 호출에 대해 사용하도록 설정되어 있지 않으면 통화 탭에서 Voicemail을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="0602b-114">Teams에서 다이얼 패드를 사용하도록 설정하기 **위한** 전제</span><span class="sxs-lookup"><span data-stu-id="0602b-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="0602b-115">Teams에서 **다이얼** 패드 탭을 사용하도록 설정하고 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 전화 시스템 및 통화 요금제에 대한 사용자를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="0602b-116">통화 계획을 설정하는 방법에 대해 알아보고자 하는 경우 통화 계획 설정 [을 읽어보아야 합니다.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="0602b-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="0602b-117">또한 Teams만 사용자에 대해 Teams 호출 정책에서 "개인 호출 허용"이 사용하도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="0602b-118">자세한 [내용은 새 Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) 관리 센터로 전환하는 동안 팀 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0602b-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="0602b-119">직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="0602b-120">직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성 을 읽어보아야 합니다.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0602b-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="0602b-121">TeamsUpgradePolicy를 사용하여 토지 호출 위치를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="0602b-122">받는 전화(및 채팅)가 Teams 또는 비즈니스용 Skype에 있는지 여부를 제어하려면 관리자는 [Microsoft](https://aka.ms/teamsadmincenter) Teams 관리 센터를 사용하거나 비즈니스용 [Skype](/powershell/module/skype) cmdlet을 사용하여 원격 Windows PowerShell TeamsUpgradePolicy를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0602b-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="0602b-123">TeamsUpgradePolicy의 기본 구성은 Teams 배포 중에 기존 비즈니스 워크플로가 중단되지 않도록 설계된 제도 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="0602b-124">기본적으로 사용자에 대한 VoIP, PSTN 및 페더링된 호출은 Teams에 인바운드 호출을 사용하도록 정책을 업데이트할 때까지 비즈니스용 Skype로 계속 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="0602b-125">받는 사람이 섬 모드인 경우:</span><span class="sxs-lookup"><span data-stu-id="0602b-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="0602b-126">비즈니스용 Skype에서 시작된 수신 VOIP 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="0602b-127">발신자 및 수신자가 동일한 테넌트에 있는 경우 Teams에서 시작된 수신 VOIP 호출은 *Teams에 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0602b-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="0602b-128">들어오는 페더리드 VOIP(클라이언트가 시작된 대상에 관계 없이) 및 PSTN 호출은 항상 받는 사람의 비즈니스용 Skype 클라이언트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="0602b-129">들어오는 VOIP 및 PSTN 호출이 항상 사용자의 Teams 클라이언트에 랜드되도록 보장하려면 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="0602b-130">공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 실행성 지침을 [참조하세요.](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="0602b-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="0602b-131">**참고 사항**</span><span class="sxs-lookup"><span data-stu-id="0602b-131">**NOTES**</span></span>
 - <span data-ttu-id="0602b-132">비즈니스용 Skype IP 휴대폰은 사용자가 TeamsOnly 모드인 경우에도 통화를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="0602b-133">비즈니스용 Skype Online에 사용할 전화 시스템 및 통화 계획 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값)는 Teams에서 사용하도록 설정되고 관리자가 관리 작업을 수행하지 않고 Teams에서 아웃바운드 PSTN 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="0602b-134">Teams에서 들어오는 모든 VOIP 및 PSTN 호출을 수신하도록 사용자를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="0602b-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="0602b-135">사용자가 Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 받을 수 있도록 Microsoft Teams 관리 센터에서 TeamsOnly로 사용자의 공존 모드를 설정하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 다음과 같이 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="0602b-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="0602b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0602b-136">See also</span></span>
[<span data-ttu-id="0602b-137">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="0602b-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="0602b-138">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="0602b-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="0602b-139">통화 플랜을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="0602b-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="0602b-140">비즈니스용 Skype PowerShell cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="0602b-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)