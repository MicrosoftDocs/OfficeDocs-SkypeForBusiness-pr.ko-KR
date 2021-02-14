---
title: 자동 전화 걸기 및 통화 큐 통화 응답
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 클라우드 자동 전화 걸기 및 통화 큐에 대해 설명하고 Teams에서 이러한 통화에 응답하는 방법을 설명하고 있습니다.
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
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766862"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="43fc8-103">자동 전화 교환에 응답하고 Teams에서 직접 큐에 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="43fc8-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="43fc8-104">Teams 사용자는 Teams 클라이언트에서 직접 클라우드 자동 전화 회의 및 통화 큐에서 전화를 받고 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="43fc8-105">자동 전화 회의 및 통화 큐란?</span><span class="sxs-lookup"><span data-stu-id="43fc8-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="43fc8-106">클라우드 자동 전화 회의는 발신자가 조직에 전화를 걸 때 사람이 아닌 음성 프롬프트 또는 오디오 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="43fc8-107">자동 전화 회의를 사용하면 발신자가 메뉴 시스템으로 이동하거나, 전화를 걸거나, 음성 인식을 사용하여 전화 키패드(DTMF) 또는 음성 입력을 사용하여 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="43fc8-108">클라우드 통화 큐에는 누군가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화 중인 사람이 대기 중인 동안 통화를 처리하기 위해 사용 가능한 다음 통화 에이전트를 검색하는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="43fc8-109">조직에 대한 단일 또는 여러 호출 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="43fc8-110">자동 전화 걸기 또는 통화 큐 호출 처리</span><span class="sxs-lookup"><span data-stu-id="43fc8-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="43fc8-111">사용자는 전화에 응답하기 전에 자동 전화 걸기 또는 통화 큐에서 수신 전화를 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="43fc8-112">각 호출에는 발신자 이름 및/또는 번호와 함께 발신자에 도달하려고 시도한 사람에 대한 정보가 포함되어 사용자에게 발신자 주소를 지정하는 더 나은 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="43fc8-113">다음 그림에서는 자동 전화 걸기 또는 통화 큐에서 수신된 통화가 사용자에게 어떻게 나타나는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![수신 전화 알림 스크린샷](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="43fc8-115">자동 전화 걸기 또는 통화 큐 통화에 응답하면 사용자는 다른 통화처럼 통화를 처리하고 다른 &#x2014; 통화를 추가하거나 전화 회의를 진행하거나 다른 파티로 통화를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="43fc8-116">또한 자동 전화 걸기 통화는 사용자의 구성에 따라 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="43fc8-117">호출 큐 호출은 사용자의 구성에 따라 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="43fc8-118">이는 에이전트가 호출에 응답할 수 있으며 호출자에 예기치 않게 전달되지 않는 한 호출자는 큐에 남아 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="43fc8-119">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="43fc8-119">Supported clients</span></span>

<span data-ttu-id="43fc8-120">자동 전화 걸기 및 통화 큐 호출에 대한 지원은 다음 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="43fc8-121">Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)</span><span class="sxs-lookup"><span data-stu-id="43fc8-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="43fc8-122">Microsoft Teams Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="43fc8-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="43fc8-123">Microsoft Teams iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="43fc8-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="43fc8-124">Microsoft Teams Android 앱</span><span class="sxs-lookup"><span data-stu-id="43fc8-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="43fc8-125">Microsoft Teams에 대한 자동 전화 걸기 및 통화 큐 지원 구성</span><span class="sxs-lookup"><span data-stu-id="43fc8-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="43fc8-126">Microsoft Teams에서 자동 전화 교환 및 통화 큐 통화를 받으하려면 상호 운영성 정책 및 업그레이드 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="43fc8-127">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 [연동성을 검토하세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="43fc8-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="43fc8-128">자동 전화 걸기 및/또는 통화 큐가 구성되어 있지 않은 경우 [](create-a-phone-system-auto-attendant.md) 클라우드 자동 전화 연결 설정 및 클라우드 통화 큐 [만들기를 참조합니다.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="43fc8-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="43fc8-129">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="43fc8-129">Known Issues</span></span>

<span data-ttu-id="43fc8-130">통화 큐 에이전트가 모바일 디바이스에서 통화를 수신하면 디바이스가 잠겨 있는 경우 통화가 보류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-130">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="43fc8-131">사용자는 먼저 디바이스의 잠금을 해제한 다음 통화에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43fc8-131">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="43fc8-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="43fc8-132">Related topics</span></span>

-    [<span data-ttu-id="43fc8-133">Microsoft 365 또는 Office 365의 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="43fc8-133">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="43fc8-134">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="43fc8-134">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="43fc8-135">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="43fc8-135">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="43fc8-136">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="43fc8-136">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

