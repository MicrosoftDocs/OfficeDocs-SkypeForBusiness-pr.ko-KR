---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: 직접 라우팅에 대 한 랜딩 페이지
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59f7cf4f1249956f3c763d12fcd96bf5c10a9fac
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "36181970"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="78b41-103">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="78b41-103">Phone System Direct Routing</span></span>

<span data-ttu-id="78b41-104">[시작](get-started-with-teams-quick-start.md)하기를 마쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="78b41-105">조직에서 [채팅, 팀, 채널, & 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 을 사용 하 여 팀을 롤아웃 했습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="78b41-106">[모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="78b41-107">이제 클라우드 음성 작업 부하를 추가할 준비가 되었으며, 전화 시스템 직접 라우팅을 사용 하 여 PSTN (공개 교환 통신망) 연결에 고유한 전화 통신 회사를 사용 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="78b41-108">직접 라우팅으로 전화 시스템을 거의 모든 통신 사업자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="78b41-109">이 문서에서는 조직의 요구 사항에 따라 직접 라우팅에 대 한 핵심 배포 결정 및 고려해 볼 수 있는 추가 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="78b41-110">Microsoft의 클라우드 음성 제공에 대 한 자세한 내용은 [Microsoft 팀에서 클라우드 음성을](cloud-voice-landing-page.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="78b41-111">직접 라우팅에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="78b41-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="78b41-112">다음 문서는 전화 시스템 다이렉트 라우팅 구성 및 사용에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="78b41-113">직접 라우팅 구성에는 PSTN 라우팅 디자인에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="78b41-114">직접 라우팅을 계획 하 고 구성 하는 방법을 이해 하려면 다음 문서를 모두 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="78b41-115">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="78b41-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="78b41-116">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="78b41-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="78b41-117">직접 라우팅으로 인증 된 세션 경계 컨트롤러 목록</span><span class="sxs-lookup"><span data-stu-id="78b41-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="78b41-118">직접 라우팅 모니터링 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="78b41-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="78b41-119">또한 요구 사항에 따라 다음 문서를 읽어 보려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="78b41-120">여러 테 넌 트에 대 한 세션 경계 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="78b41-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="78b41-121">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="78b41-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="78b41-122">PSTN 연결을 사용 하는 하이브리드 환경의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="78b41-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="78b41-123">직접 라우팅에 대해 자세히 알아보려면 다음 세션을 시청 하세요. [Microsoft 팀의 직접 라우팅](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="78b41-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="78b41-124">핵심 배포 결정</span><span class="sxs-lookup"><span data-stu-id="78b41-124">Core deployment decisions</span></span>

<span data-ttu-id="78b41-125">이는 직접 라우팅에 대해 고려해 야 할 핵심 결정 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="78b41-126">질문 하기</span><span class="sxs-lookup"><span data-stu-id="78b41-126">Ask yourself</span></span>|<span data-ttu-id="78b41-127">함수</span><span class="sxs-lookup"><span data-stu-id="78b41-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="78b41-128">사용자가 직접 라우팅을 사용할 수 있도록 설정 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="78b41-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="78b41-129">자세한 내용은 [직접 라우팅 서비스에 대 한 사용자 사용](direct-routing-configure.md#enable-users-for-direct-routing-service)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="78b41-130">직접 라우팅에 필요한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="78b41-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="78b41-131">자세한 내용은 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="78b41-132">SBC (세션 경계 컨트롤러) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="78b41-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="78b41-133">직접 라우팅이 있으면 자체의 SBC (세션 경계 컨트롤러)을 전화 시스템에 직접 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="78b41-134">인증 된 SBCs 목록은 [지원 되는 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="78b41-135">질문 하기</span><span class="sxs-lookup"><span data-stu-id="78b41-135">Ask yourself</span></span>|<span data-ttu-id="78b41-136">함수</span><span class="sxs-lookup"><span data-stu-id="78b41-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="78b41-137">SBCs를 배포 하는 위치는 어디 인가요?</span><span class="sxs-lookup"><span data-stu-id="78b41-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="78b41-138">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="78b41-139">여러 테 넌 트가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="78b41-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="78b41-140">자세한 내용은 [여러 테 넌 트에 대 한 세션 경계 컨트롤러 구성을](direct-routing-sbc-multiple-tenants.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="78b41-141">음성 라우팅 고려 사항</span><span class="sxs-lookup"><span data-stu-id="78b41-141">Voice routing considerations</span></span>

<span data-ttu-id="78b41-142">특정 SBCs에 게 통화를 라우팅하려면 전화 시스템을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="78b41-143">질문 하기</span><span class="sxs-lookup"><span data-stu-id="78b41-143">Ask yourself</span></span>|<span data-ttu-id="78b41-144">함수</span><span class="sxs-lookup"><span data-stu-id="78b41-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="78b41-145">만들어야 할 음성 라우팅 정책, PSTN 사용 및 음성 경로는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="78b41-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="78b41-146">음성 라우팅에 대 한 자세한 내용은 [음성 라우팅 구성을](direct-routing-configure.md#configure-voice-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="78b41-147">내가 정의한 음성 라우팅 정책에 어떤 사용자를 할당 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="78b41-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="78b41-148">[음성 라우팅 구성](direct-routing-configure.md#configure-voice-routing)의 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="78b41-149">통화 및 interop 정책</span><span class="sxs-lookup"><span data-stu-id="78b41-149">Calling and interop policies</span></span>

<span data-ttu-id="78b41-150">직접 라우팅은 Microsoft 팀 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="78b41-151">직접 라우팅을 통해 PSTN 전화를 걸거나 받으려면 팀에서 수신 전화를 받을 수 있도록 필요한 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="78b41-152">팀 전용 모드로 사용자를 구성 하거나 TeamsCallingPolicy 및 TeamsInteropPolicy를 할당 하 여 기본 호출 클라이언트로 팀을 구성 하 여 팀을 기본 클라이언트로 설정 하도록 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="78b41-153">질문 하기</span><span class="sxs-lookup"><span data-stu-id="78b41-153">Ask yourself</span></span>|<span data-ttu-id="78b41-154">함수</span><span class="sxs-lookup"><span data-stu-id="78b41-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="78b41-155">팀을 기본 통화 클라이언트로 설정 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="78b41-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="78b41-156">자세한 내용은 [Microsoft 팀을 사용자를 위한 기본 호출 클라이언트로 설정을](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="78b41-157">추가 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="78b41-157">Additional deployment considerations</span></span>

<span data-ttu-id="78b41-158">조직의 요구 및 구성에 따라 다음을 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78b41-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="78b41-159">질문 하기</span><span class="sxs-lookup"><span data-stu-id="78b41-159">Ask yourself</span></span>| <span data-ttu-id="78b41-160">함수</span><span class="sxs-lookup"><span data-stu-id="78b41-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="78b41-161">하이브리드 연결을 사용 하는 기존 비즈니스용 Skype 서버 배포가 구성 되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="78b41-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="78b41-162">하이브리드 환경의 사용자 계정을 프로 비전 하 고 관리 하는 방법을 이해 하려면 [PSTN 연결을 사용 하는 하이브리드 환경에서 사용자 계정을](direct-routing-user-accounts-in-a-hybrid-environment.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="78b41-163">통화 요금제에서 직접 라우팅 하거나 비즈니스용 Skype 온-프레미스 환경에서 마이그레이션하는 경우</span><span class="sxs-lookup"><span data-stu-id="78b41-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="78b41-164">기존 환경에서 직접 라우팅으로 마이그레이션하는 방법에 대 한 자세한 내용은 [직접 라우팅으로 마이그레이션을](direct-routing-migrating.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="78b41-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
