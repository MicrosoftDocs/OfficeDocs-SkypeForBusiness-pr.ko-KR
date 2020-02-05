---
title: 클라우드 통화 큐 계획
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환을 사용 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: 24a0bba82ef38288f5c96cc7c51ce1bfb88c8f05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735228"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="7e2b5-103">클라우드 통화 큐 계획</span><span class="sxs-lookup"><span data-stu-id="7e2b5-103">Plan Cloud call queues</span></span>

<span data-ttu-id="7e2b5-104">클라우드 통화 큐는 고객 통화를 수락 하 고, 인사말 메시지를 재생 한 후 이러한 호출에 응답 하도록 미리 구성 된 에이전트 목록을 검색 하는 동안 이러한 호출을 대기 큐에 배치 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="7e2b5-105">메일 사용이 가능한 메일 그룹이 나 보안 그룹의 에이전트 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="7e2b5-106">조직에는 하나 또는 여러 개의 통화 큐가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="7e2b5-107">통화 큐는 일반적으로 자동 전화 교환과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="7e2b5-108">또한 클라우드 통화 큐에서 다음을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="7e2b5-109">발신자가 대기 중인 동안 음악</span><span class="sxs-lookup"><span data-stu-id="7e2b5-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="7e2b5-110">통화 큐 최대 크기, 시간 제한 및 통화 처리 옵션에 대 한 사용자 지정 설정</span><span class="sxs-lookup"><span data-stu-id="7e2b5-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="7e2b5-111">각 호출 큐에는 Microsoft 팀 관리 센터의 통화 큐에 직접 연결 될 비즈니스용 Skype 서버 2019 시스템에서 **리소스 계정** ( [구성 리소스 계정](configure-onprem-ra.md)참조)이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7e2b5-112">통화 큐에 대 한 자세한 내용을 보려면 [클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue) 및 통화 큐에 대해 존재 하는 옵션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="7e2b5-113">여러 전화 번호를 통화 큐에 할당할 수 있지만 Microsoft 서비스 번호 또는 하이브리드 번호 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e2b5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e2b5-114">Requirements</span></span>

<span data-ttu-id="7e2b5-115">다음 요구 사항에 따라 지원 되는 토폴로지에 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="7e2b5-116">요구 사항은 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="7e2b5-117">클라우드 통화 큐를 새로 구성 하려면 [리소스 계정 구성](configure-onprem-ra.md)에 설명 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="7e2b5-118">온라인 또는 비즈니스용 Skype 서버 2019에 리소스 계정을 만들어야 하며 전화 번호를 통화 큐와 연결 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="7e2b5-119">위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 통화 큐 서비스에 연결 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="7e2b5-120">하이브리드 연결</span><span class="sxs-lookup"><span data-stu-id="7e2b5-120">Hybrid connectivity.</span></span> <span data-ttu-id="7e2b5-121">비즈니스용 Skype 서버가 이미 배포 되어 있고 온-프레미스 사용자에 대해 클라우드 통화 큐를 사용 하도록 설정 하려는 경우 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="7e2b5-122">이를 분할 도메인 구성 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="7e2b5-123">자세한 내용은 비즈니스용 [Skype 서버 및 office 365의 하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="7e2b5-124">리소스 계정에 전화 번호를 할당 하는 경우 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="7e2b5-125">이렇게 하면 조직 수준의 전화 번호에 전화 시스템 기능이 제공 되며, 자동 전화 교환 및 전화 큐 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="7e2b5-126">각 통화 큐에 대해 온-프레미스 [리소스 계정을](configure-onprem-ra.md) 만들고 필요한 경우 라이선스 및 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="7e2b5-127">추가 계획 리소스</span><span class="sxs-lookup"><span data-stu-id="7e2b5-127">Additional planning resources</span></span>

<span data-ttu-id="7e2b5-128">[Small business 예-Set up a auto attendant](/microsoftteams/tutorial-org-aa) 는 사용자 요구 사항에 대 한 정보를 수집 하 고, 자동 전화 교환 및 사용자의 구조를 계획 하 고, 메뉴 음성 안내를 작성 하 고, 온라인 관리 센터에서 계획을 구현 하는 프로세스를 통해 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="7e2b5-129">자습서를 검토 하 고 여기에 있는 연습을 사용 하 여 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="7e2b5-130">사용자의 요구에 맞는 견고한 구조와 고객을 효율적으로 안내 하는 스크립트를 만들려면 [리소스 계정 구성을](configure-onprem-ra.md)계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2b5-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e2b5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e2b5-131">See Also</span></span>

[<span data-ttu-id="7e2b5-132">리소스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="7e2b5-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="7e2b5-133">전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용</span><span class="sxs-lookup"><span data-stu-id="7e2b5-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="7e2b5-134">클라우드 자동 전화 교환 이란?</span><span class="sxs-lookup"><span data-stu-id="7e2b5-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="7e2b5-135">클라우드 자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="7e2b5-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="7e2b5-136">비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜</span><span class="sxs-lookup"><span data-stu-id="7e2b5-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="7e2b5-137">비즈니스용 Skype 서버 및 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="7e2b5-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="7e2b5-138">Microsoft 팀의 자원 계정 관리</span><span class="sxs-lookup"><span data-stu-id="7e2b5-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
