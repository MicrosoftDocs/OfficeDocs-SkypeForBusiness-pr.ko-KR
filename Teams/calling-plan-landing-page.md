---
title: Microsoft Teams에서 계획 호출
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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Teams의 Cloud Voice에서 조직에 가장 적합한 Microsoft Phone System 호출 계획을 결정합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102734"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="1d867-103">사용자에게 적합한 통화 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1d867-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="1d867-104">시작 을 [완료한 것입니다.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="1d867-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="1d867-106">회의 를 통해 [모임을 & 수 있습니다.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="1d867-107">이제 클라우드 음성 워크로드를 추가할 준비가 됐고, PSTN(공용 전환 전화 네트워크)에 연결하기 위해 통화 계획과 함께 Microsoft Phone System을 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="1d867-108">이 문서에서는 호출 계획에 대한 핵심 배포 결정과 조직의 요구에 따라 구성하려는 추가 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="1d867-109">Microsoft의 클라우드 음성 제공에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="1d867-110">통화 계획에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="1d867-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="1d867-111">다음 문서에서는 Microsoft 호출 요금제 배포 및 사용에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="1d867-112">Microsoft 365 또는 Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="1d867-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="1d867-113">Microsoft 365 또는 Office 365 요금제 호출</span><span class="sxs-lookup"><span data-stu-id="1d867-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="1d867-114">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="1d867-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="1d867-115">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="1d867-115">Core deployment decisions</span></span>

<span data-ttu-id="1d867-116">Microsoft를 전화 통신 사업자로 사용하려면 전화 요금제 라이선스를 획득하고 휴대폰 시스템 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="1d867-117">사용할 수 있는 통화 계획에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="1d867-118">국내 통화 계획</span><span class="sxs-lookup"><span data-stu-id="1d867-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="1d867-119">국내 및 국제 통화 계획</span><span class="sxs-lookup"><span data-stu-id="1d867-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="1d867-120">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="1d867-120">Ask yourself</span></span>|<span data-ttu-id="1d867-121">작업</span><span class="sxs-lookup"><span data-stu-id="1d867-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="1d867-122">내 지역에서 통화 요금제를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1d867-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="1d867-123">통화 계획 서비스가 있는 사용자 위치는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="1d867-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="1d867-124">자세한 내용은 오디오 회의 및 통화 계획에 대한 국가 및 지역 [가용성을 참조하세요.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="1d867-125">내 사용자에게 국제 통화가 필요합니까?</span><span class="sxs-lookup"><span data-stu-id="1d867-125">Do my users need international calling?</span></span> | <span data-ttu-id="1d867-126">자세한 내용은 [Microsoft 365 또는 Office 365 요금제 호출을 참조하세요.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="1d867-127">내 사용자에게 통화 계획 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="1d867-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="1d867-128">라이선스를 구입하고 할당하는 경우 2단계: 라이선스 구입 [및 할당을 참조합니다.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="1d867-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="1d867-129">각 사용자에게 DID(직접 내선 다이얼) 전화 번호가 있나요?</span><span class="sxs-lookup"><span data-stu-id="1d867-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="1d867-130">전화 번호를 얻은 경우 [3단계: 전화 번호 를 를 참조합니다.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="1d867-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="1d867-131">Microsoft 365 또는 Office 365로 전화 번호 전송</span><span class="sxs-lookup"><span data-stu-id="1d867-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="1d867-132">현재 서비스 공급자에서 Teams로 전화 번호를 쉽게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="1d867-133">휴대폰 번호를 Teams로 포트한 후 Microsoft는 서비스 공급자가 되고 해당 전화 번호에 대한 요금을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="1d867-134">자세한 내용은 Teams로 [전화 번호 전송을 참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="1d867-135">전화번호와 긴급 위치</span><span class="sxs-lookup"><span data-stu-id="1d867-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="1d867-136">Microsoft 365 또는 Office 365에서 통화 계획을 사용할 경우 조직의 모든 사용자는 고유한 직접 전화 번호(DID) 전화 번호와 해당 유효성이 검사된 긴급 주소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="1d867-137">비상 주소(예: 사무실 번호 또는 바닥 번호) 내에서 응급 위치를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="1d867-138">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="1d867-138">Ask yourself</span></span>|<span data-ttu-id="1d867-139">작업</span><span class="sxs-lookup"><span data-stu-id="1d867-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1d867-140">긴급 주소 및 위치 정보를 얼마나 자세히 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="1d867-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="1d867-141">자세한 내용은 긴급 위치, 주소 및 통화 [라우팅이란? 을 참조하세요.](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="1d867-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="1d867-142">ID 호출</span><span class="sxs-lookup"><span data-stu-id="1d867-142">Calling identity</span></span>

<span data-ttu-id="1d867-143">기본적으로 모든 아웃바운드 호출은 할당된 전화 번호를 호출 ID(발신자 ID)로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="1d867-144">전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d867-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="1d867-145">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="1d867-145">Ask yourself</span></span>|<span data-ttu-id="1d867-146">작업</span><span class="sxs-lookup"><span data-stu-id="1d867-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1d867-147">발신자 ID를 마스크하거나 사용하지 않도록 설정하나요?</span><span class="sxs-lookup"><span data-stu-id="1d867-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="1d867-148">호출자 ID를 변경하거나 차단하는 경우 사용자에 대한 [발신자 ID 설정 을 참조합니다.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="1d867-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||