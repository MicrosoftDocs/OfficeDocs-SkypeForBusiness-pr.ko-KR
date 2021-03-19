---
title: 자동 참석자 응답 및 큐 호출
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Cloud 자동 참석자 및 호출 큐를 설명하고 Teams에서 이러한 호출에 응답하는 방법을 설명합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874668"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="60620-103">자동 전화 교환에 응답하고 Teams에서 직접 큐에 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="60620-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="60620-104">Teams 사용자는 Cloud 자동 참석자로부터 전화를 받고 응답하고 Teams 클라이언트에서 직접 큐를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="60620-105">자동 참석자 및 호출 큐란?</span><span class="sxs-lookup"><span data-stu-id="60620-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="60620-106">클라우드 자동 참석자는 조직에 전화를 걸 때 사용자 연산자 대신 발신자가 듣는 일련의 음성 프롬프트 또는 오디오 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="60620-107">자동 참석자는 음성 인식을 사용하여 전화 키패드(DTMF) 또는 음성 입력을 사용하여 발신자가 메뉴 시스템을 이동하거나, 전화를 걸거나, 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="60620-108">클라우드 호출 큐에는 다른 사용자가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화 중인 사용자가 대기 중이면서 통화를 처리하기 위해 사용할 수 있는 다음 통화 에이전트를 검색하는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="60620-109">조직에 대해 단일 또는 여러 개의 호출 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="60620-110">자동 참석자 또는 호출 큐 호출 처리</span><span class="sxs-lookup"><span data-stu-id="60620-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="60620-111">사용자는 전화에 응답하기 전에 자동 참석자 또는 통화 큐에서 들어오는 호출을 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="60620-112">발신자 이름 및/또는 수와 함께 각 호출에는 발신자에 도달하려는 사람에 대한 정보가 포함되어 사용자에게 발신자 주소를 지정하기 위한 더 나은 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="60620-113">다음 그림에서는 자동 참석자 또는 통화 큐에서 들어오는 호출이 사용자에게 어떻게 나타나는지 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="60620-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![들어오는 통화 알림 스크린샷](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="60620-115">자동 참석자 또는 통화 큐 호출에 응답하면 사용자가 다른 사용자에서 추가 또는 회의를 추가하거나 다른 &#x2014; 다른 통화와 같이 통화를 처리 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="60620-116">또한 사용자의 구성에 따라 자동 참석자 호출이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="60620-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="60620-117">호출 큐 호출은 사용자의 구성에 따라 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="60620-118">이는 에이전트가 호출에 응답할 수 있으며 발신자는 예기치 않게 전달되지 않는 때까지 발신자는 큐에 남아 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="60620-119">에이전트는 통화 큐 호출에 대한 부재 중 전화 또는 음성 메일에 대해 알림을 들이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="60620-120">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="60620-120">Supported clients</span></span>

<span data-ttu-id="60620-121">자동 참석자 및 호출 큐 호출에 대한 지원은 다음 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="60620-122">Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="60620-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="60620-123">Microsoft Teams Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="60620-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="60620-124">Microsoft Teams iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="60620-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="60620-125">Microsoft Teams Android 앱</span><span class="sxs-lookup"><span data-stu-id="60620-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="60620-126">Microsoft Teams에 대한 자동 참석자 및 호출 큐 지원 구성</span><span class="sxs-lookup"><span data-stu-id="60620-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="60620-127">Microsoft Teams에서 자동 참석을 수신하고 큐 호출을 수신하려면 상호 운영성 정책 및 업그레이드 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="60620-128">비즈니스용 Skype와 함께 Teams를 사용하는 조직의 마이그레이션 및 상호 [연동성을 검토하세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="60620-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="60620-129">자동 참석자 및/또는 호출 큐가 구성되지 않은 경우 클라우드 [](create-a-phone-system-auto-attendant.md) 자동 참석자 설정 및 클라우드 호출 큐 만들기를 [참조합니다.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="60620-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="60620-130">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="60620-130">Known Issues</span></span>

<span data-ttu-id="60620-131">통화 큐 에이전트가 모바일 디바이스에서 전화를 받으면 디바이스가 잠겨 있는 경우 통화가 보류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60620-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="60620-132">사용자는 먼저 디바이스의 잠금을 해제한 다음 통화에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60620-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="60620-133">관련 주제</span><span class="sxs-lookup"><span data-stu-id="60620-133">Related topics</span></span>

-    [<span data-ttu-id="60620-134">Microsoft 365 또는 Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="60620-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="60620-135">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="60620-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="60620-136">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="60620-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="60620-137">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="60620-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

