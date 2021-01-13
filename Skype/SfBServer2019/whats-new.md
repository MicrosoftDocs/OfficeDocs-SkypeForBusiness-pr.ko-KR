---
title: 비즈니스용 Skype 서버 2019의 새로운 계획 | 기능
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 이러한 기능은 비즈니스용 Skype 서버 2019의 새로운 기능입니다.'
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812588"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="6d5ff-103">비즈니스용 Skype 서버 2019의 경우</span><span class="sxs-lookup"><span data-stu-id="6d5ff-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="6d5ff-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2019의 새로운 기능에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="6d5ff-105">비즈니스용 Skype 서버 2019의 새로운 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="6d5ff-106">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="6d5ff-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="6d5ff-107">호출 데이터 커넥터</span><span class="sxs-lookup"><span data-stu-id="6d5ff-107">Call Data Connector</span></span>
- <span data-ttu-id="6d5ff-108">단계적 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="6d5ff-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="6d5ff-109">통합 메시징 서비스: Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="6d5ff-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="6d5ff-110">Exchange UM은 비즈니스용 Skype 2019와 Exchange 2013 또는 Exchange 2016을 통합할 때 비즈니스용 Skype 서버에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="6d5ff-111">Exchange 2019의 지원이 변경되어 Cloud Voicemail 및 Cloud 자동 전화 교환 Exchange UM 통합이 강조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="6d5ff-112">Cloud Voicemail을 사용하면 모든 비즈니스용 Skype 2019 사용자가&#x2014;또는 온라인&#x2014;Microsoft 클라우드의 동일한 음성메일 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="6d5ff-113">Cloud Voicemail은 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="6d5ff-114">비즈니스용 Skype Online, Teams 또는 Outlook 클라이언트를 사용하여 Exchange 사서함의 음성 메일에 액세스</span><span class="sxs-lookup"><span data-stu-id="6d5ff-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="6d5ff-115">웹 기반 포털을 사용하여 음성메일 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="6d5ff-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="6d5ff-116">자세한 [내용은 클라우드 음성메일](../sfbhybrid/hybrid/plan-cloud-voicemail.md) 서비스 계획 및 비즈니스용 Skype Exchange Server [마이그레이션을](../sfbhybrid/hybrid/plan-um-migration.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="6d5ff-117">통화 모니터링: 통화 데이터 커넥터</span><span class="sxs-lookup"><span data-stu-id="6d5ff-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="6d5ff-118">통화 데이터 커넥터는 더 이상 여러 가지 설정의 On-premises 및 Online 도구 집합을 사용하여 모든 사용자의 통화 품질을 모니터링할 필요가 아니기 때문에 하이브리드 환경에서 통화 모니터링을 크게 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="6d5ff-119">사용자가 온-프레미스에 있는지 온라인에 있는지에 따라 전체 조직에 대한 통화 품질을 온라인으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="6d5ff-120">Call Data Connector를 사용하면 단일 도구 집합을 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="6d5ff-121">Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype 서버에서 사용자 환경을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="6d5ff-122">네트워크 전체의 문제 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6d5ff-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="6d5ff-123">기술 지원 팀 작업자가 자신의 책임 영역을 보고 문제를 해결할 수 있도록 Call Analytics에 대한 지원 데스크 및 관리자 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="6d5ff-124">자세한 내용은 통화 데이터 커넥터 계획(Plan [Call Data Connector)을](../sfbhybrid/hybrid/plan-call-data-connector.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="6d5ff-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d5ff-125">See also</span></span>

[<span data-ttu-id="6d5ff-126">비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ff-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
