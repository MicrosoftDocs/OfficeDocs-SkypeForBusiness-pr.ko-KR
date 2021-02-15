---
title: 클라우드 통화 큐 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 회의를 사용하는 방법을 간략하게 소개합니다.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918744"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="8d4a1-103">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="8d4a1-103">Plan Cloud call queues</span></span>

<span data-ttu-id="8d4a1-104">클라우드 통화 큐는 고객 통화를 수락하고 인사말 메시지를 재생한 다음 미리 구성된 에이전트 목록을 검색하여 이러한 통화를 대기 큐에 저장하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="8d4a1-105">메일 사용이 가능한 메일 그룹 또는 보안 그룹에서 에이전트 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="8d4a1-106">조직에 통화 큐가 하나 이상일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="8d4a1-107">통화 큐는 일반적으로 자동 전화 걸기와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="8d4a1-108">또한 클라우드 통화 큐는 다음을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="8d4a1-109">음악 대기 중일 때</span><span class="sxs-lookup"><span data-stu-id="8d4a1-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="8d4a1-110">통화 큐 최대 크기, 제한 시간 및 통화 처리 옵션에 대한 사용자 지정 설정</span><span class="sxs-lookup"><span data-stu-id="8d4a1-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="8d4a1-111">각 통화 큐에는  Microsoft Teams [](configure-onprem-ra.md)관리 센터의 통화 큐에 직접 연결될 비즈니스용 Skype 서버 2019 시스템에서 리소스 계정(리소스 계정 구성 참조)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8d4a1-112">통화 [큐의](/MicrosoftTeams/create-a-phone-system-call-queue) 기능과 통화 큐에 대한 옵션 및 기능에 대한 자세한 내용은 클라우드 통화 큐 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="8d4a1-113">여러 전화 번호를 통화 큐에 할당할 수 있지만 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="8d4a1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d4a1-114">Requirements</span></span>

<span data-ttu-id="8d4a1-115">다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버 2019를 이미 배포했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="8d4a1-116">요구 사항은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="8d4a1-117">클라우드 통화 큐의 새 구성은 리소스 계정 구성에 설명된 [단계를 따릅니다.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="8d4a1-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="8d4a1-118">온라인 또는 비즈니스용 Skype 서버 2019에서 리소스 계정을 만들어야 하며 전화 번호를 통화 큐와 연결해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="8d4a1-119">위의 요구 사항 외에도 Microsoft 클라우드 통화 큐 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="8d4a1-120">하이브리드 연결.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-120">Hybrid connectivity.</span></span> <span data-ttu-id="8d4a1-121">비즈니스용 Skype 서버가 이미 배포되어 있으며, 비즈니스용 Skype 사용자에 대해 클라우드 통화 큐를 사용하도록 설정하려는 경우, 하이브리드 연결이 프레미스 환경과 온라인 환경 간에 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="8d4a1-122">이를 분할 도메인 구성이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="8d4a1-123">자세한 내용은 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 비즈니스용 [Skype 서버와 Microsoft 365 또는 Office 365](configure-hybrid-connectivity.md)간의 하이브리드 연결 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="8d4a1-124">리소스 계정에 전화 번호를 할당하는 경우 이제 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="8d4a1-125">이렇게 하면 조직 수준의 전화 번호에 전화 시스템 기능이 제공될 수 있으며 자동 전화 걸기 및 통화 큐 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="8d4a1-126">각 통화 큐에 [](configure-onprem-ra.md) 대해 프레미스 리소스 계정을 만들고 필요한 경우 라이선스 및 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8d4a1-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="8d4a1-127">요구 사항을 충족하는 견고한 구조와 고객을 효율적으로 안내하는 스크립트가 있는 경우 리소스 계정 [구성을 진행합니다.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="8d4a1-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d4a1-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d4a1-128">See Also</span></span>

[<span data-ttu-id="8d4a1-129">리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="8d4a1-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="8d4a1-130">전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용</span><span class="sxs-lookup"><span data-stu-id="8d4a1-130">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="8d4a1-131">클라우드 자동 전화 교환이란?</span><span class="sxs-lookup"><span data-stu-id="8d4a1-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="8d4a1-132">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="8d4a1-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="8d4a1-133">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획</span><span class="sxs-lookup"><span data-stu-id="8d4a1-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="8d4a1-134">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="8d4a1-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="8d4a1-135">Microsoft Teams에서 리소스 계정 관리</span><span class="sxs-lookup"><span data-stu-id="8d4a1-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
