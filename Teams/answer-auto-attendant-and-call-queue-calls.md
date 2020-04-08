---
title: 자동 전화 교환 및 통화 대기열 통화 응답
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 클라우드 자동 전화 교환 및 통화 대기열에 대해 설명 하 고 팀에서 이러한 통화에 응답 하는 방법에 대해 설명 합니다.
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
ms.openlocfilehash: 80400d9e9d7ab1519a15ab299f07896f55342eaf
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190862"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="47567-103">자동 전화 교환에 응답하고 Teams에서 직접 큐에 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="47567-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="47567-104">팀 사용자는 자신의 팀 클라이언트에서 직접 클라우드 자동 전화 교환 및 통화 대기열에서 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="47567-105">자동 전화 교환 및 통화 대기열 이란?</span><span class="sxs-lookup"><span data-stu-id="47567-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="47567-106">클라우드 자동 전화 교환 기능을 통해 조직에 전화를 거는 경우 사용자가 직접 교환원 대신 듣는 오디오 파일 및 일련의 음성 메시지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47567-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="47567-107">자동 전화 교환을 통해 발신자는 전화 키패드 (DTMF) 또는 음성 인식 기능을 사용 하 여 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="47567-108">클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화를 자동으로 대기 하는 기능, 전화를 걸고 있는 사용자가 대기 중인 음악을 수신 대기 하는 동안 사용 가능한 다음 통화 에이전트를 검색 하 여 통화를 처리 하는 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47567-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="47567-109">조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="47567-110">자동 전화 교환 또는 통화 대기열 통화 처리</span><span class="sxs-lookup"><span data-stu-id="47567-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="47567-111">사용자는 전화를 받기 전에 자동 전화 교환 또는 통화 대기열에서 걸려오는 전화를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="47567-112">각 통화에는 호출자의 이름 및/또는 번호와 함께 호출자가 연락을 시도한 사람에 대 한 정보가 포함 되어 사용자에 게 호출자의 주소를 지정 하는 데 더 나은 컨텍스트를 제공 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47567-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="47567-113">다음 그림에서는 자동 전화 교환 또는 통화 대기열에서 걸려온 통화가 사용자에 게 표시 되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47567-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![수신 전화 알림 스크린샷](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="47567-115">자동 전화 교환 또는 통화 대기열 전화에 응답 한 후에는 다른 통화와 같은 통화를 처리할 수 &#x2014;,이 경우 사용자는 상대방과 회의를 추가 하거나 다른 사용자에 게 통화를 이전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="47567-116">또한 자동 전화 교환 호출은 사용자의 구성을 기반으로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47567-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="47567-117">통화 대기열 호출은 사용자의 구성을 기반으로 착신 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="47567-118">에이전트에서 전화를 받을 수 있고 호출자가 예기치 않게 착신 전환 되지 않을 때까지 호출자가 큐에 유지 되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47567-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="47567-119">지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="47567-119">Supported clients</span></span>

<span data-ttu-id="47567-120">자동 전화 교환 및 통화 대기열 통화에 대 한 지원은 다음 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47567-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="47567-121">Microsoft 팀 Windows 클라이언트 (32 및 64 비트 버전)</span><span class="sxs-lookup"><span data-stu-id="47567-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="47567-122">Microsoft 팀 Mac 클라이언트</span><span class="sxs-lookup"><span data-stu-id="47567-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="47567-123">Microsoft 팀 iPhone 앱</span><span class="sxs-lookup"><span data-stu-id="47567-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="47567-124">Microsoft 팀 Android 앱</span><span class="sxs-lookup"><span data-stu-id="47567-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="47567-125">Microsoft 팀에 대 한 자동 전화 교환 및 통화 대기열 지원 구성</span><span class="sxs-lookup"><span data-stu-id="47567-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="47567-126">Microsoft 팀에서 자동 전화 교환 및 통화 대기열 통화를 받으려면 상호 운용성 정책 및 업그레이드 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47567-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="47567-127">[비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성](migration-interop-guidance-for-teams-with-skype.md)을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="47567-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="47567-128">자동 전화 교환 및/또는 통화 대기열이 구성 되어 있지 않은 경우이 작업을 수행 하려면 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md) 및 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47567-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="47567-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="47567-129">Related topics</span></span>

-    [<span data-ttu-id="47567-130">Office 365의 전화 시스템 소개</span><span class="sxs-lookup"><span data-stu-id="47567-130">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="47567-131">클라우드 통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="47567-131">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="47567-132">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="47567-132">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="47567-133">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="47567-133">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

