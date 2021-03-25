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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필수 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122212"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="b5419-103">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="b5419-103">Phone System Direct Routing</span></span>

<span data-ttu-id="b5419-104">[시작](get-started-with-teams-quick-start.md)을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="b5419-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="b5419-106">회의 를 통해 [모임을 & 수 있습니다.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="b5419-107">이제 클라우드 음성 워크로드를 추가할 준비가 됐고, 전화 시스템 직접 라우팅을 사용하여 PSTN(공용 전환 전화 네트워크) 연결을 위해 자체 전화 통신 회사를 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="b5419-108">직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="b5419-109">이 문서에서는 조직의 요구에 따라 고려할 수 있는 추가 고려 사항뿐만 아니라 직접 라우팅에 대한 핵심 배포 결정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="b5419-110">Microsoft의 클라우드 음성 제공에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="b5419-111">직접 라우팅에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b5419-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="b5419-112">다음 문서에서는 전화 시스템 직접 라우팅 구성 및 사용에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="b5419-113">직접 라우팅을 구성하려면 PSTN 라우팅 디자인을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="b5419-114">직접 라우팅을 계획하고 구성하는 방법을 이해하기 위해 다음 문서를 모두 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="b5419-115">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="b5419-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="b5419-116">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="b5419-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="b5419-117">직접 라우팅으로 인증된 SBC(Session Border Controller) 목록</span><span class="sxs-lookup"><span data-stu-id="b5419-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="b5419-118">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b5419-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="b5419-119">또한 요구 사항에 따라 다음 문서를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="b5419-120">여러 테넌트에 대해 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="b5419-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="b5419-121">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b5419-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="b5419-122">PSTN 연결이 포함된 하이브리드 환경의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="b5419-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="b5419-123">Microsoft Teams에서 직접 라우팅: 직접 라우팅에 대한 자세한 내용은 다음 세션을 [시청합니다.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="b5419-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="b5419-124">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="b5419-124">Core deployment decisions</span></span>

<span data-ttu-id="b5419-125">직접 라우팅에 대해 고려해야 할 핵심 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="b5419-126">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="b5419-126">Ask yourself</span></span>|<span data-ttu-id="b5419-127">작업</span><span class="sxs-lookup"><span data-stu-id="b5419-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="b5419-128">어떤 사용자가 직접 라우팅을 사용하도록 설정하나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="b5419-129">자세한 내용은 직접 라우팅 서비스에 대한 사용자 [사용 을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="b5419-130">직접 라우팅에 필요한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="b5419-131">자세한 내용은 라이선스 및 기타 [요구 사항을 참조하세요.](direct-routing-plan.md#licensing-and-other-requirements)</span><span class="sxs-lookup"><span data-stu-id="b5419-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="b5419-132">SBC(세션 테두리 컨트롤러) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b5419-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="b5419-133">직접 라우팅을 사용하면 전화 시스템에 직접 SBC(세션 테두리 컨트롤러)를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="b5419-134">인증된 SBC 목록은 지원되는 [세션 테두리 컨트롤러 를 참조하세요.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="b5419-135">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="b5419-135">Ask yourself</span></span>|<span data-ttu-id="b5419-136">작업</span><span class="sxs-lookup"><span data-stu-id="b5419-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b5419-137">SBC를 어디서 어떻게 배포하나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="b5419-138">자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="b5419-139">테넌트가 여러 개 있나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="b5419-140">자세한 내용은 여러 테넌트에 대한 세션 테두리 [컨트롤러 구성을 참조하세요.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="b5419-141">음성 라우팅 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b5419-141">Voice routing considerations</span></span>

<span data-ttu-id="b5419-142">호출을 특정 SBC로 라우팅하도록 전화 시스템을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="b5419-143">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="b5419-143">Ask yourself</span></span>|<span data-ttu-id="b5419-144">작업</span><span class="sxs-lookup"><span data-stu-id="b5419-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b5419-145">어떤 음성 라우팅 정책, PSTN 사용 및 음성 경로를 만들어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="b5419-146">음성 라우팅 정보는 음성 라우팅 구성 [을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="b5419-147">정의한 음성 라우팅 정책에 할당되는 사용자는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="b5419-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="b5419-148">음성 라우팅 구성 의 [예제를 참조합니다.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="b5419-149">TeamsUpgradePolicy를 사용하여 Teams 클라이언트에서 들어오는 호출이 토지가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="b5419-150">직접 라우팅은 Microsoft Teams에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="b5419-151">직접 라우팅을 통해 PSTN 호출을 수신하려면 Teams에서 들어오는 호출이 수신되도록 TeamsUpgradePolicy를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="b5419-152">사용자는 Teams Only 모드에 있어야 합니다. 이 모드는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당하여 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="b5419-153">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="b5419-153">Ask yourself</span></span>|<span data-ttu-id="b5419-154">작업</span><span class="sxs-lookup"><span data-stu-id="b5419-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="b5419-155">Teams Only 모드는 무엇을 의미하나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="b5419-156">자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침을 [참조하세요.](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="b5419-157">추가 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b5419-157">Additional deployment considerations</span></span>

<span data-ttu-id="b5419-158">조직의 요구 사항 및 구성에 따라 다음을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5419-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="b5419-159">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="b5419-159">Ask yourself</span></span>| <span data-ttu-id="b5419-160">작업</span><span class="sxs-lookup"><span data-stu-id="b5419-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="b5419-161">하이브리드 연결이 구성된 기존 비즈니스용 Skype Server 배포가 있나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="b5419-162">하이브리드 환경의 사용자 계정이 프로비전 및 관리되는 방법을 이해하기 위해 PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 [참조합니다.](direct-routing-user-accounts-in-a-hybrid-environment.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="b5419-163">통화 계획 또는 비즈니스용 Skype온-프레미스 환경에서 직접 라우팅으로 마이그레이션하나요?</span><span class="sxs-lookup"><span data-stu-id="b5419-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="b5419-164">기존 환경에서 직접 라우팅으로 마이그레이션하는 방법을 더 이해하려면 직접 라우팅으로 마이그레이션을 [참조합니다.](direct-routing-migrating.md)</span><span class="sxs-lookup"><span data-stu-id="b5419-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||