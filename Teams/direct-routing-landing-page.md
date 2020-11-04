---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필요한 핵심 배포 결정, 음성 라우팅 고려 사항 등의 직접적인 라우팅에 대해 자세히 알아보세요.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 172253f0c1fe99043a21bf70309d81f71e392d4c
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878522"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="8d0c5-103">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="8d0c5-103">Phone System Direct Routing</span></span>

<span data-ttu-id="8d0c5-104">[시작](get-started-with-teams-quick-start.md)을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="8d0c5-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="8d0c5-106">[모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="8d0c5-107">이제 클라우드 음성 작업 부하를 추가할 준비가 되었으며, 전화 시스템 직접 라우팅을 사용 하 여 PSTN (공개 교환 통신망) 연결에 고유한 전화 통신 회사를 사용 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="8d0c5-108">직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="8d0c5-109">이 문서에서는 조직의 요구 사항에 따라 직접 라우팅에 대 한 핵심 배포 결정 및 고려해 볼 수 있는 추가 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="8d0c5-110">Microsoft의 클라우드 음성 제공에 대 한 자세한 내용은 [Microsoft 팀에서 클라우드 음성을](cloud-voice-landing-page.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="8d0c5-111">직접 라우팅에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="8d0c5-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="8d0c5-112">다음 문서는 전화 시스템 다이렉트 라우팅 구성 및 사용에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="8d0c5-113">직접 라우팅 구성에는 PSTN 라우팅 디자인에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="8d0c5-114">직접 라우팅을 계획 하 고 구성 하는 방법을 이해 하려면 다음 문서를 모두 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="8d0c5-115">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="8d0c5-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="8d0c5-116">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="8d0c5-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="8d0c5-117">직접 라우팅으로 인증된 SBC(Session Border Controller) 목록</span><span class="sxs-lookup"><span data-stu-id="8d0c5-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="8d0c5-118">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8d0c5-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="8d0c5-119">또한 요구 사항에 따라 다음 문서를 읽어 보려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="8d0c5-120">여러 테넌트에 대해 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="8d0c5-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="8d0c5-121">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8d0c5-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="8d0c5-122">PSTN 연결이 포함된 하이브리드 환경의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="8d0c5-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="8d0c5-123">직접 라우팅에 대해 자세히 알아보려면 다음 세션을 시청 하세요. [Microsoft 팀의 직접 라우팅](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="8d0c5-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="8d0c5-124">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="8d0c5-124">Core deployment decisions</span></span>

<span data-ttu-id="8d0c5-125">이는 직접 라우팅에 대해 고려해 야 할 핵심 결정 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="8d0c5-126">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="8d0c5-126">Ask yourself</span></span>|<span data-ttu-id="8d0c5-127">작업</span><span class="sxs-lookup"><span data-stu-id="8d0c5-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="8d0c5-128">사용자가 직접 라우팅을 사용할 수 있도록 설정 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="8d0c5-129">자세한 내용은 [직접 라우팅 서비스에 대 한 사용자 사용](direct-routing-configure.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="8d0c5-130">직접 라우팅에 필요한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="8d0c5-131">자세한 내용은 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="8d0c5-132">SBC (세션 경계 컨트롤러) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8d0c5-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="8d0c5-133">직접 라우팅이 있으면 자체의 SBC (세션 경계 컨트롤러)을 전화 시스템에 직접 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="8d0c5-134">인증 된 SBCs 목록은 [지원 되는 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="8d0c5-135">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="8d0c5-135">Ask yourself</span></span>|<span data-ttu-id="8d0c5-136">작업</span><span class="sxs-lookup"><span data-stu-id="8d0c5-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8d0c5-137">SBCs를 배포 하는 위치는 어디 인가요?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="8d0c5-138">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="8d0c5-139">여러 테 넌 트가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="8d0c5-140">자세한 내용은 [여러 테 넌 트에 대 한 세션 경계 컨트롤러 구성을](direct-routing-sbc-multiple-tenants.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="8d0c5-141">음성 라우팅 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8d0c5-141">Voice routing considerations</span></span>

<span data-ttu-id="8d0c5-142">특정 SBCs에 게 통화를 라우팅하려면 전화 시스템을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="8d0c5-143">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="8d0c5-143">Ask yourself</span></span>|<span data-ttu-id="8d0c5-144">작업</span><span class="sxs-lookup"><span data-stu-id="8d0c5-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8d0c5-145">만들어야 할 음성 라우팅 정책, PSTN 사용 및 음성 경로는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="8d0c5-146">음성 라우팅에 대 한 자세한 내용은 [음성 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="8d0c5-147">내가 정의한 음성 라우팅 정책에 어떤 사용자를 할당 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="8d0c5-148">[음성 라우팅 구성](direct-routing-configure.md)의 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="8d0c5-149">TeamsUpgradePolicy를 사용 하 여 팀 클라이언트에서 걸려오는 전화가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8d0c5-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="8d0c5-150">직접 라우팅은 Microsoft 팀 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="8d0c5-151">직접 라우팅을 통해 PSTN 통화를 받으려면 팀에서 수신 전화를 받을 수 있도록 TeamsUpgradePolicy를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="8d0c5-152">사용자는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스에 할당 하 여 팀 전용 모드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="8d0c5-153">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="8d0c5-153">Ask yourself</span></span>|<span data-ttu-id="8d0c5-154">작업</span><span class="sxs-lookup"><span data-stu-id="8d0c5-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8d0c5-155">팀 전용 모드의 의미</span><span class="sxs-lookup"><span data-stu-id="8d0c5-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="8d0c5-156">자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="8d0c5-157">추가 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8d0c5-157">Additional deployment considerations</span></span>

<span data-ttu-id="8d0c5-158">조직의 요구 및 구성에 따라 다음을 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="8d0c5-159">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="8d0c5-159">Ask yourself</span></span>| <span data-ttu-id="8d0c5-160">작업</span><span class="sxs-lookup"><span data-stu-id="8d0c5-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8d0c5-161">하이브리드 연결을 사용 하는 기존 비즈니스용 Skype 서버 배포가 구성 되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="8d0c5-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="8d0c5-162">하이브리드 환경의 사용자 계정을 프로 비전 하 고 관리 하는 방법을 이해 하려면 [PSTN 연결을 사용 하는 하이브리드 환경에서 사용자 계정을](direct-routing-user-accounts-in-a-hybrid-environment.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="8d0c5-163">통화 요금제에서 직접 라우팅 하거나 비즈니스용 Skype 온-프레미스 환경에서 마이그레이션하는 경우</span><span class="sxs-lookup"><span data-stu-id="8d0c5-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="8d0c5-164">기존 환경에서 직접 라우팅으로 마이그레이션하는 방법에 대 한 자세한 내용은 [직접 라우팅으로 마이그레이션을](direct-routing-migrating.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0c5-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
