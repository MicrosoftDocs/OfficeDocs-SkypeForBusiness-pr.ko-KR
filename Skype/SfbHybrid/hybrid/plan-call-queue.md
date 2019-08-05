---
title: 클라우드 통화 대기열 계획
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환을 사용 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185544"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="10475-103">클라우드 통화 대기열 계획</span><span class="sxs-lookup"><span data-stu-id="10475-103">Plan Cloud call queues</span></span>

<span data-ttu-id="10475-104">클라우드 통화 큐는 고객 전화를 수락 하 고, 인사말 메시지를 재생 한 다음, 미리 구성 된 에이전트 목록을 검색 하 여 이러한 통화에 응답 하는 동안 대기 대기열에 이러한 호출을 배치 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="10475-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="10475-105">메일 사용이 가능한 메일 그룹이 나 보안 그룹의 에이전트 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="10475-106">조직에는 하나 또는 여러 개의 통화 대기열이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="10475-107">통화 대기열은 일반적으로 자동 전화 교환와 조합 하 여 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10475-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="10475-108">또한 클라우드 통화 대기열은 다음을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="10475-109">호출자가 대기 중인 동안 음악</span><span class="sxs-lookup"><span data-stu-id="10475-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="10475-110">통화 대기열에 대 한 사용자 지정 설정 최대 크기, 시간 제한 및 통화 처리 옵션</span><span class="sxs-lookup"><span data-stu-id="10475-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="10475-111">Microsoft 팀 관리 센터의 통화 대기열에 직접 연결 되는 비즈니스용 Skype Server 2019 시스템에서 각 통화 대기열에는 **리소스 계정** ( [리소스 계정 구성](configure-onprem-ra.md)참조)이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10475-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="10475-112">통화 대기열에 대 한 자세한 내용 및 통화 대기열에 대해 존재 하는 옵션과 기능은 [클라우드 통화 대기열 만들기](/MicrosoftTeams/create-a-phone-system-call-queue) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10475-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="10475-113">여러 전화 번호를 통화 대기열에 할당할 수 있지만, Microsoft 서비스 번호 또는 하이브리드 번호 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="10475-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10475-114">Requirements</span></span>

<span data-ttu-id="10475-115">다음 요구 사항은 지원 되는 토폴로지에서 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="10475-116">요구 사항은 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="10475-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="10475-117">클라우드 통화 큐의 새로운 구성을 보려면 [리소스 계정 구성](configure-onprem-ra.md)에 설명 된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10475-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="10475-118">온라인 또는 비즈니스용 Skype 서버 2019에 리소스 계정을 만들어야 하며 전화 번호를 통화 대기열과 연결 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="10475-119">위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 통화 대기열 서비스에 연결 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="10475-120">하이브리드 연결.</span><span class="sxs-lookup"><span data-stu-id="10475-120">Hybrid connectivity.</span></span> <span data-ttu-id="10475-121">비즈니스용 Skype 서버를 이미 배포 하 고 온-프레미스 사용자에 대 한 클라우드 호출 큐를 사용 하도록 설정 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="10475-122">이를 도메인 분할 구성이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="10475-123">자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="10475-124">리소스 계정에 전화 번호를 지정 하는 경우, 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="10475-125">이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10475-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="10475-126">각 통화 대기열에 대 한 온-프레미스 [리소스 계정을](configure-onprem-ra.md) 만들고 필요한 경우 라이선스 및 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="10475-127">추가 계획 리소스</span><span class="sxs-lookup"><span data-stu-id="10475-127">Additional planning resources</span></span>

<span data-ttu-id="10475-128">사용자 요구에 대 한 정보를 수집 하는 프로세스, 자동 전화 교환 및 사용자의 구조 계획, 메뉴 프롬프트를 작성 하는 등의 간단한 비즈니스와 같은 자습서에서 [자동 전화 교환을 설정](/microsoftteams/tutorial-org-aa) 하면 온라인 관리 센터에서 계획을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="10475-129">자습서를 검토 하 고 여기에서 계획 수립 연습을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="10475-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="10475-130">사용자의 요구에 맞는 솔리드 구조와 고객을 효율적으로 안내 하는 스크립트를 사용 하는 경우 [리소스 계정 구성을](configure-onprem-ra.md)진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="10475-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10475-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10475-131">See Also</span></span>

[<span data-ttu-id="10475-132">자원 계정 구성</span><span class="sxs-lookup"><span data-stu-id="10475-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="10475-133">전화 사용자 인터페이스를 사용 하 여 사용자 지정 음성 안내 기록 사용</span><span class="sxs-lookup"><span data-stu-id="10475-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="10475-134">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="10475-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="10475-135">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="10475-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="10475-136">비즈니스용 Skype 서버와 Office 365 하이브리드 연결 계획</span><span class="sxs-lookup"><span data-stu-id="10475-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="10475-137">비즈니스용 Skype 서버와 Office 365 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="10475-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="10475-138">Microsoft 팀에서 자원 계정 관리</span><span class="sxs-lookup"><span data-stu-id="10475-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
