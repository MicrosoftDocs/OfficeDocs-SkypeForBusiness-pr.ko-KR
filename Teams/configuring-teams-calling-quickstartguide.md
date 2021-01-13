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
description: 사용자 집합을 시작하고 실행하기 위해 Microsoft Teams에서 통화 계획을 구성하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799768"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="30a98-103">빠른 시작 가이드: Microsoft Teams의 통화 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="30a98-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="30a98-104">이 가이드는 Teams에서 통화 계획을 탐색할 수 있도록 사용자 집합을 설정하고 실행하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="30a98-105">2017년 12월 12일, Teams의 통화 계획 발표: [Intelligent Communications는 Teams에서](https://aka.ms/ipyqus) 통화하는 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="30a98-106">이 빠른 시작 가이드와 병렬로 통화 계획 [](calling-plan-landing-page.md) 및 [FastTrack을](https://aka.ms/cloudvoice) 통해 전화 시스템을 읽고 성공적인 출시를 계획하고 진행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="30a98-107">비즈니스용 Skype에서 제공한 Microsoft 365 및 Office 365 기능인 통화 요금제를 추가하면 이제 Teams를 사용하여 PSTN(공용 전화망)을 통해 유선 및 휴대폰으로 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="30a98-109">Teams에서 통화 탭을 사용하도록 설정하기 **위한** 전제</span><span class="sxs-lookup"><span data-stu-id="30a98-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="30a98-110">Teams 사용자의  통화 탭을 사용하려면 Teams에서 1:1 통화를 사용하도록 설정하고 1:1 Teams 통화를 지원하는 Teams 클라이언트를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="30a98-111">Teams에서 1:1 통화를 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy를 읽어보아야 합니다.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="30a98-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="30a98-112">통화를 지원하는 클라이언트를 알아보고 Microsoft Teams에 대한 제한 및 [사양을 읽어 보아야 합니다.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)</span><span class="sxs-lookup"><span data-stu-id="30a98-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="30a98-113">현재 사용자가 PSTN 통화를 사용하도록 설정되어 있지 않으면 통화 탭에서 음성메일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="30a98-114">Teams에서 다이얼 패드를 사용하도록 설정하기 위한 **전제**</span><span class="sxs-lookup"><span data-stu-id="30a98-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="30a98-115">Teams에서 **다이얼** 패드 탭을 사용하도록 설정하고 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용하려면 전화 시스템 및 통화 요금제에 대한 사용자를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="30a98-116">통화 요금제 설정 방법에 대한 [](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)자세한 내용은 통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="30a98-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="30a98-117">또한 Teams 사용자만 Teams 통화 정책에서 "비공개 통화 허용"을 사용하도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="30a98-118">자세한 [내용은 새 Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) 관리 센터로 전환하는 동안 Teams 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30a98-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="30a98-119">직접 라우팅을 사용하여 사용자가 PSTN 통화를 걸고 받을 수 있도록 허용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="30a98-120">직접 라우팅을 설정하는 방법에 대한 자세한 내용은 직접 라우팅 [구성을 읽어 읽습니다.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="30a98-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="30a98-121">TeamsUpgradePolicy를 사용하여 호출 위치 제어</span><span class="sxs-lookup"><span data-stu-id="30a98-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="30a98-122">수신 전화(및 채팅)가 Teams 또는 비즈니스용 [Skype에](https://docs.microsoft.com/powershell/module/skype) 있는지 여부를 제어하기 위해 관리자는 [Microsoft Teams](https://aka.ms/teamsadmincenter) 관리 센터 또는 비즈니스용 Skype cmdlet과의 원격 Windows PowerShell 세션을 사용하여 TeamsUpgradePolicy를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="30a98-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="30a98-123">TeamsUpgradePolicy의 기본 구성은 Teams 배포 중에 기존 비즈니스 워크플로가 중단되지 않도록 설계된 제도 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="30a98-124">기본적으로 VoIP, PSTN 및 사용자에 대한 페더링된 통화는 Teams로의 인바운드 통화를 사용하도록 정책을 업데이트할 때까지 비즈니스용 Skype로 계속 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="30a98-125">받는 사람이 제도 모드에 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="30a98-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="30a98-126">비즈니스용 Skype에서 시작된 수신 VOIP 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="30a98-127">Teams에서 시작된 수신 VOIP 호출은 보낸 사람 및 받는 사람이 동일한 테넌트에 있는 경우 *Teams에 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="30a98-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="30a98-128">받는 페더러드 VOIP(클라이언트가 시작된 클라이언트에 관계 없이) 및 PSTN 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="30a98-129">들어오는 VOIP 및 PSTN 호출이 항상 사용자의 Teams 클라이언트에 연결되도록하려면 사용자의 공존 모드를 TeamsOnly로 업데이트합니다(즉, TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당).</span><span class="sxs-lookup"><span data-stu-id="30a98-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="30a98-130">공존 모드 및 TeamsUpgradePolicy에 대한 자세한 내용은 [비즈니스용 Skype와](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30a98-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="30a98-131">**참고 사항**</span><span class="sxs-lookup"><span data-stu-id="30a98-131">**NOTES**</span></span>
 - <span data-ttu-id="30a98-132">사용자가 TeamsOnly 모드인 경우에도 비즈니스용 Skype IP 전화기에서 전화를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="30a98-133">비즈니스용 Skype Online에서 사용하기 위해 전화 시스템 및 통화 요금제 라이선스로 프로비전된 사용자(예: OnlineVoiceRoutingPolicy의 값이 할당된 사용자)는 Teams에서 통화 탭을 사용하도록 설정하고 관리자가 관리 작업을 수행하지 않고도 Teams에서 아웃바운드 PSTN 통화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="30a98-134">Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 받도록 사용자를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="30a98-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="30a98-135">사용자가 Teams에서 들어오는 모든 VOIP 및 PSTN 통화를 수신하도록 Microsoft Teams 관리 센터에서 사용자의 공존 모드를 TeamsOnly로 설정하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 다음과 같이 TeamsUpgradePolicy를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30a98-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="30a98-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30a98-136">See also</span></span>
[<span data-ttu-id="30a98-137">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="30a98-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="30a98-138">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="30a98-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="30a98-139">통화 플랜을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="30a98-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="30a98-140">비즈니스용 Skype PowerShell cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="30a98-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

