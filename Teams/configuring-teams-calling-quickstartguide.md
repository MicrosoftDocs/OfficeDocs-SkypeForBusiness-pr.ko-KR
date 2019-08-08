---
title: 빠른 시작 가이드-Microsoft 팀에서 전화 요금제 구성
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Microsoft 팀에서 통화 계획을 구성 하기 위한 빠른 시작 가이드입니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e043633749e0ef2dba41b5b3b18776cfbe1c497
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236856"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="00dec-103">빠른 시작 가이드: Microsoft 팀에서 통화 계획 구성</span><span class="sxs-lookup"><span data-stu-id="00dec-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="00dec-104">이 가이드는 팀에서 통화 계획을 탐색할 수 있도록 사용자 집합을 준비 하 고 실행 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="00dec-105">12 월 12 일, 2017, 팀의 통화 계획 공지 사항: [지능형 통신은 팀에서 호출 하는 다음 단계를 수행 합니다](https://aka.ms/ipyqus) .</span><span class="sxs-lookup"><span data-stu-id="00dec-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="00dec-106">이 빠른 시작 가이드를 사용 하 여 통화 요금제와 [Fasttrack](https://aka.ms/cloudvoice) 을 함께 사용 하 여 성공적인 출시를 계획 하 고 구동 하는 방법으로 [전화 시스템](calling-plan-landing-page.md) 을 읽을 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="00dec-107">통화 계획 추가-비즈니스용 Skype에서 제공 하는 Office 365 기능-이제 팀을 사용 하 여 PSTN (공공 교환 전화 네트워크)을 통해 지역 및 휴대폰으로 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![팀의 연락처 페이지를 보여주는 스크린샷](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="00dec-109">팀에서 **통화** 탭을 사용 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="00dec-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="00dec-110">팀에서 **통화** 탭을 사용 하도록 설정 하려면 팀에서 1:1 통화를 사용 하도록 설정 하 고 1:1 팀 호출을 지 원하는 팀 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="00dec-111">팀에서 1:1 통화를 관리 하는 방법에 대 한 자세한 내용은 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00dec-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="00dec-112">전화를 지 원하는 클라이언트에 [대 한 자세한 내용은 Microsoft 팀에 대 한 제한 사항 및 사양을](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00dec-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="00dec-113">현재, 사용자가 PSTN 통화를 사용 하도록 설정 하지 않은 경우에는 통화 탭에서 음성 메일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="00dec-114">팀에서 **다이얼 패드** 를 사용 하기 위한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="00dec-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="00dec-115">팀에서 **다이얼 패드** 탭을 사용 하도록 설정 하 고 사용자가 PSTN 통화를 설정 하 고 수신할 수 있도록 하려면 전화 시스템 및 통화 요금제에 대 한 사용자를 프로 비전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="00dec-116">통화 계획을 설정 하는 방법에 대 한 자세한 내용은 [통화 계획 설정을](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00dec-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="00dec-117">또한 직접 라우팅을 사용 하 여 사용자가 PSTN 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="00dec-118">직접 라우팅을 설정 하는 방법에 대 한 자세한 내용은 [직접 라우팅 구성을](https://docs.microsoft.com/microsoftteams/direct-routing-configure)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00dec-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="00dec-119">TeamsUpgradePolicy를 사용 하 여 전화를 거는 위치 제어</span><span class="sxs-lookup"><span data-stu-id="00dec-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="00dec-120">팀 또는 비즈니스용 Skype에서 걸려오는 통화 (및 채팅)가 어디에 있는지 제어 하기 위해 관리자는 [Microsoft 팀 관리 센터](https://aka.ms/teamsadmincenter) 를 사용 하거나 [비즈니스용 Skype](https://docs.microsoft.com/powershell/module/skype) 에서 원격 Windows PowerShell 세션을 사용 하 여 TeamsUpgradePolicy를 사용 합니다. cmdlet.</span><span class="sxs-lookup"><span data-stu-id="00dec-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="00dec-121">TeamsUpgradePolicy의 기본 구성은 팀을 배포 하는 동안 기존 비즈니스 워크플로가 중단 되지 않도록 설계 된 아일랜드 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="00dec-122">기본적으로 사용자에 대 한 VoIP, PSTN 및 페더레이션된 통화는 팀에 대 한 인바운드 호출을 사용 하도록 정책을 업데이트할 때까지 계속 해 서 비즈니스용 Skype로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="00dec-123">받는 사람이 아일랜드 모드일 때:</span><span class="sxs-lookup"><span data-stu-id="00dec-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="00dec-124">비즈니스용 Skype에서 시작 된 수신 VOIP 통화는 항상 받는 사람의 비즈니스용 Skype 클라이언트에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="00dec-125">*발신자와 수신자가 동일한 테 넌 트에 있는 경우*팀에서 생성 된 수신 VOIP 통화</span><span class="sxs-lookup"><span data-stu-id="00dec-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="00dec-126">들어오는 페더레이션 VOIP (클라이언트의 연결 여부에 관계 없음) 및 PSTN 호출은 항상 받는 사람의 Skype for Business 클라이언트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="00dec-127">들어오는 VOIP 및 PSTN 통화가 사용자의 팀 클라이언트에 항상 존재 하도록 하려면 사용자의 공존 모드를 팀 전용으로 업데이트 하세요 (즉, "UpgradeToTeams" 인스턴스를 할당 하는 것을 의미 함).</span><span class="sxs-lookup"><span data-stu-id="00dec-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="00dec-128">공존 모드 및 TeamsUpgradePolicy에 대 한 자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00dec-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="00dec-129">**상속자**</span><span class="sxs-lookup"><span data-stu-id="00dec-129">**NOTES**</span></span>
 - <span data-ttu-id="00dec-130">비즈니스용 Skype IP 전화는 사용자가 TeamsOnly 모드에 있더라도 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="00dec-131">Skype for Business Online에서 사용할 수 있도록 전화 시스템 및 통화 계획 라이선스로 프로 비전 된 사용자 (예: OnlineVoiceRoutingPolicy 값이 지정 된 경우)는 팀에서 통화 탭을 사용 하도록 설정 하 고 아웃 바운드 PSTN 통화를 관리자가 없는 팀은 관리 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="00dec-132">팀에서 모든 수신 VOIP 및 PSTN 통화를 받도록 사용자를 구성 하는 방법</span><span class="sxs-lookup"><span data-stu-id="00dec-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="00dec-133">사용자가 팀에서 모든 수신 VOIP 및 PSTN 통화를 받을 수 있도록 하려면 사용자의 공존 모드를 Microsoft 팀 관리 센터 에서만 TeamsOnly로 설정 하거나 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용 하 여 다음과 같이 TeamsUpgradePolicy를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="00dec-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="00dec-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00dec-134">See also</span></span>
[<span data-ttu-id="00dec-135">통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="00dec-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="00dec-136">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="00dec-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="00dec-137">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="00dec-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="00dec-138">비즈니스용 Skype PowerShell cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="00dec-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

