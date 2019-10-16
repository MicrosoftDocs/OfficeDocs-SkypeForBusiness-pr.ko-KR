---
title: Microsoft 팀의 통화 계획
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
description: 통화 계획 랜딩 페이지
appliesto:
- Microsoft Teams
ms.openlocfilehash: 998c0964239e430451a157bb6d8d0034fc7d19a7
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517002"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="7cb2e-103">사용자에 게 적합 한 통화 요금제는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="7cb2e-104">[시작](get-started-with-teams-quick-start.md)하기를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="7cb2e-105">조직에서 [채팅, 팀, 채널, & 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 을 사용 하 여 팀을 롤아웃 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="7cb2e-106">[모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="7cb2e-107">이제 클라우드 음성 작업 부하를 추가할 준비가 되었고, 통화 요금제로 Microsoft 전화 시스템을 사용 하 여 PSTN (공개 교환 전화 네트워크)에 연결 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="7cb2e-108">이 문서에서는 조직의 요구 사항에 따라, 호출 계획에 대 한 핵심 배포 의사 결정과 구성할 수 있는 추가 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="7cb2e-109">Microsoft의 클라우드 음성 제공에 대 한 자세한 내용은 [Microsoft 팀에서 클라우드 음성을](cloud-voice-landing-page.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="7cb2e-110">통화 요금제에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7cb2e-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="7cb2e-111">다음 문서는 Microsoft 통화 계획 배포 및 사용에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="7cb2e-112">Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="7cb2e-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="7cb2e-113">Office 365에 대 한 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="7cb2e-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="7cb2e-114">통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="7cb2e-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="7cb2e-115">핵심 배포 결정</span><span class="sxs-lookup"><span data-stu-id="7cb2e-115">Core deployment decisions</span></span>

<span data-ttu-id="7cb2e-116">Microsoft를 전화 통신 회사로 사용 하려면 통화 요금제 라이선스를 얻고 전화 시스템 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="7cb2e-117">사용할 수 있는 통화 계획에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="7cb2e-118">국내 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="7cb2e-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="7cb2e-119">국내 및 국제 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="7cb2e-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="7cb2e-120">질문 하기</span><span class="sxs-lookup"><span data-stu-id="7cb2e-120">Ask yourself</span></span>|<span data-ttu-id="7cb2e-121">함수</span><span class="sxs-lookup"><span data-stu-id="7cb2e-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="7cb2e-122">내 지역에서 사용 가능한 통화 요금제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="7cb2e-123">요금제 서비스를 호출할 사용자 위치</span><span class="sxs-lookup"><span data-stu-id="7cb2e-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="7cb2e-124">자세한 내용은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="7cb2e-125">사용자에 게 국제 통화가 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-125">Do my users need international calling?</span></span> | <span data-ttu-id="7cb2e-126">자세한 내용은 [Office 365에 대 한 요금제 호출](calling-plans-for-office-365.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="7cb2e-127">내 사용자가 통화 계획 라이선스를 보유 하 고 있나요?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="7cb2e-128">라이선스를 구입 하 여 할당 하려면 [2 단계: 라이선스 구입 및 할당](set-up-calling-plans.md#step-2-buy-and-assign-licenses)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="7cb2e-129">사용자에 게 직접 바로 안쪽 전화 접속 (a) 전화 번호를 사용 하 고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="7cb2e-130">전화 번호를 얻으려면 [3 단계: 전화 번호 받기를](set-up-calling-plans.md#step-3-get-phone-numbers)참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="7cb2e-131">Office 365에 전화 번호 전송</span><span class="sxs-lookup"><span data-stu-id="7cb2e-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="7cb2e-132">현재 서비스 공급자에서 팀으로 전화 번호를 쉽게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="7cb2e-133">전화 번호를 팀으로 이식 하면 Microsoft가 서비스 공급자가 되며 해당 전화 번호로 청구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="7cb2e-134">자세한 내용은 [Office 365으로 전화 번호 전송을](transfer-phone-numbers-to-office-365.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="7cb2e-135">전화 번호 및 비상 위치</span><span class="sxs-lookup"><span data-stu-id="7cb2e-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="7cb2e-136">Office 365의 통화 요금제를 사용 하는 경우 조직의 모든 사용자에 게 고유한 직접 안쪽 전화 접속 (a) 전화 번호 및 해당 하 고 확인 된 긴급 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="7cb2e-137">긴급 주소 내에서 비상 위치 (예: 사무실 번호 또는 바닥 번호)를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="7cb2e-138">질문 하기</span><span class="sxs-lookup"><span data-stu-id="7cb2e-138">Ask yourself</span></span>|<span data-ttu-id="7cb2e-139">함수</span><span class="sxs-lookup"><span data-stu-id="7cb2e-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="7cb2e-140">긴급 주소 및 위치 정보를 자세히 확인 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="7cb2e-141">자세한 내용은 [긴급 위치, 주소 및 통화 라우팅 이란?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="7cb2e-142">통화 id</span><span class="sxs-lookup"><span data-stu-id="7cb2e-142">Calling identity</span></span>

<span data-ttu-id="7cb2e-143">기본적으로 모든 아웃 바운드 통화는 지정 된 전화 번호를 통화 id (발신자 ID)로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="7cb2e-144">통화를 받는 사람은 발신자를 빠르게 확인 하 고 통화 수락 또는 거부 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="7cb2e-145">질문 하기</span><span class="sxs-lookup"><span data-stu-id="7cb2e-145">Ask yourself</span></span>|<span data-ttu-id="7cb2e-146">함수</span><span class="sxs-lookup"><span data-stu-id="7cb2e-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="7cb2e-147">발신자 ID를 마스킹 또는 사용 하지 않도록 설정 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="7cb2e-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="7cb2e-148">발신자 ID를 변경 하거나 차단 하려면 [사용자의 발신자 Id 설정을](set-the-caller-id-for-a-user.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb2e-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




