---
title: Microsoft Teams에서 통화 계획
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
description: Teams의 Cloud Voice에서 조직에 가장 적합한 Microsoft 전화 시스템 통화 계획을 결정하십시오.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031854"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="f59de-103">사용자에게 적합한 통화 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f59de-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="f59de-104">시작을 [완료합니다.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="f59de-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="f59de-105">조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="f59de-106">회의에 모임을 & [수도 있습니다.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="f59de-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="f59de-107">이제 클라우드 음성 워크로드를 추가할 준비가 됐고, PSTN(공용 전화망)에 연결하기 위해 통화 계획과 함께 Microsoft Phone System을 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="f59de-108">이 문서에서는 통화 계획에 대한 핵심 배포 결정과 조직의 요구에 따라 구성하려는 추가 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="f59de-109">또한 Microsoft의 클라우드 음성 제안에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="f59de-110">통화 요금제에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="f59de-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="f59de-111">다음 문서에서는 Microsoft 통화 요금제 배포 및 사용에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="f59de-112">Microsoft 365 또는 Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="f59de-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="f59de-113">Microsoft 365 또는 Office 365용 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="f59de-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="f59de-114">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="f59de-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="f59de-115">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="f59de-115">Core deployment decisions</span></span>

<span data-ttu-id="f59de-116">Microsoft를 통신사로 사용하려면 통화 요금제 라이선스를 획득하여 전화 시스템 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="f59de-117">사용할 수 있는 통화 요금제에는 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="f59de-118">국내 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="f59de-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="f59de-119">국내 및 국제 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="f59de-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="f59de-120">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f59de-120">Ask yourself</span></span>|<span data-ttu-id="f59de-121">작업</span><span class="sxs-lookup"><span data-stu-id="f59de-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f59de-122">통화 요금제는 내 지역에서 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f59de-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="f59de-123">통화 요금제 서비스를 사용할 사용자 위치는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f59de-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="f59de-124">자세한 내용은 오디오 회의 및 통화 요금제에 대한 국가 및 지역 [가용성을 참조하세요.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="f59de-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="f59de-125">내 사용자에게 국제 통화가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="f59de-125">Do my users need international calling?</span></span> | <span data-ttu-id="f59de-126">자세한 내용은 [Microsoft 365 또는 Office 365에](calling-plans-for-office-365.md)대한 통화 요금제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f59de-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="f59de-127">내 사용자에게 통화 요금제 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f59de-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="f59de-128">라이선스를 구입하고 할당하기 위해 2단계: 라이선스 구입 [및 할당을 참조합니다.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="f59de-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="f59de-129">각 사용자에게는 DID(직접 전화 번호) 전화 번호가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f59de-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="f59de-130">전화 번호를 얻습니다. [3단계: 전화 번호 보기를 참조합니다.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="f59de-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="f59de-131">Microsoft 365 또는 Office 365로 전화 번호 이전</span><span class="sxs-lookup"><span data-stu-id="f59de-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="f59de-132">현재 서비스 공급자에서 Teams로 전화 번호를 쉽게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="f59de-133">전화 번호를 Teams로 포식하면 Microsoft가 서비스 공급자가 되고 해당 전화 번호에 대한 요금을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="f59de-134">자세한 내용은 Teams로 전화 [번호 이전을 참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f59de-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="f59de-135">전화번호와 긴급 위치</span><span class="sxs-lookup"><span data-stu-id="f59de-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="f59de-136">Microsoft 365 또는 Office 365의 통화 요금제에서는 조직의 모든 사용자에게 고유한 DID(직접 전화 번호) 전화 번호와 확인된 해당 긴급 주소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="f59de-137">긴급 주소 내에서 긴급 위치(예: 사무실 번호 또는 층 번호)를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="f59de-138">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f59de-138">Ask yourself</span></span>|<span data-ttu-id="f59de-139">작업</span><span class="sxs-lookup"><span data-stu-id="f59de-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f59de-140">긴급 주소 및 위치 정보를 얼마나 자세히 원하나요?</span><span class="sxs-lookup"><span data-stu-id="f59de-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="f59de-141">자세한 내용은 긴급 [위치,](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)주소 및 통화 라우팅이란?</span><span class="sxs-lookup"><span data-stu-id="f59de-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="f59de-142">ID 호출</span><span class="sxs-lookup"><span data-stu-id="f59de-142">Calling identity</span></span>

<span data-ttu-id="f59de-143">기본적으로 모든 아웃바운드 호출은 발신자 ID(발신자 ID)로 할당된 전화 번호를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="f59de-144">전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59de-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="f59de-145">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f59de-145">Ask yourself</span></span>|<span data-ttu-id="f59de-146">작업</span><span class="sxs-lookup"><span data-stu-id="f59de-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f59de-147">호출자 ID를 마스킹하거나 사용하지 않도록 설정하나요?</span><span class="sxs-lookup"><span data-stu-id="f59de-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="f59de-148">발신자 ID를 변경하거나 차단하는 경우 사용자의 호출자 [ID 설정을 참조합니다.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f59de-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




