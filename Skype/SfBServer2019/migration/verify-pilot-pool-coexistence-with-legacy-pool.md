---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 파일럿 풀과 레거시 풀의 동시 사용 여부를 확인하는 프로세스입니다.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751660"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="06afb-103">레거시 풀로 파일럿 풀 동시 사용 확인</span><span class="sxs-lookup"><span data-stu-id="06afb-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="06afb-104">**이 문서의**</span><span class="sxs-lookup"><span data-stu-id="06afb-104">**In this article**</span></span>
  
[<span data-ttu-id="06afb-105">비즈니스용 Skype 서버 2019 서비스가 시작된지 확인</span><span class="sxs-lookup"><span data-stu-id="06afb-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="06afb-106">비즈니스용 Skype 서버 2019 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="06afb-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="06afb-107">레거시 토폴로지 작성기에서 토폴로지 열지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="06afb-108">파일럿 풀을 배포한 후 관리 도구를 사용하여 풀 정보를 살펴보면서 두 풀이 모두 존재하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="06afb-109">비즈니스용 Skype 서버 2019 풀 및 레거시 풀의 경우 비즈니스용 Skype 서버 2019 제어판 및 토폴로지 작성기 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="06afb-110">비즈니스용 Skype 서버 2019 서비스가 시작된지 확인</span><span class="sxs-lookup"><span data-stu-id="06afb-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="06afb-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="06afb-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="06afb-112">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 관리 도구\서비스 애플릿으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="06afb-113">프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="06afb-114">중앙 로깅 서비스 에이전트</span><span class="sxs-lookup"><span data-stu-id="06afb-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="06afb-115">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="06afb-115">Application Sharing</span></span>
    - <span data-ttu-id="06afb-116">오디오 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="06afb-116">Audio Test Service</span></span>
    - <span data-ttu-id="06afb-117">오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="06afb-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="06afb-118">Call Park</span><span class="sxs-lookup"><span data-stu-id="06afb-118">Call Park</span></span>
    - <span data-ttu-id="06afb-119">회의 공지</span><span class="sxs-lookup"><span data-stu-id="06afb-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="06afb-120">회의 참석자</span><span class="sxs-lookup"><span data-stu-id="06afb-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="06afb-121">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="06afb-121">Front-End</span></span>
    - <span data-ttu-id="06afb-122">IM 회의</span><span class="sxs-lookup"><span data-stu-id="06afb-122">IM Conferencing</span></span>
    - <span data-ttu-id="06afb-123">중재</span><span class="sxs-lookup"><span data-stu-id="06afb-123">Mediation</span></span>
    - <span data-ttu-id="06afb-124">복제본 복제자 에이전트</span><span class="sxs-lookup"><span data-stu-id="06afb-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="06afb-125">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="06afb-125">Response Group</span></span>
    - <span data-ttu-id="06afb-126">웹 회의</span><span class="sxs-lookup"><span data-stu-id="06afb-126">Web Conferencing</span></span>
    - <span data-ttu-id="06afb-127">XMPP Translating Gateway</span><span class="sxs-lookup"><span data-stu-id="06afb-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="06afb-128">비즈니스용 Skype 서버 2019 제어판 열기</span><span class="sxs-lookup"><span data-stu-id="06afb-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="06afb-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="06afb-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="06afb-130">비즈니스용 Skype 서버 2019 배포의 프런트 엔드 서버에서 비즈니스용 Skype 서버 2019 제어판을 열고 레거시 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="06afb-131">절차를 반복하여 비즈니스용 Skype 서버 2019 풀을 여는 과정을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="06afb-132">비즈니스용 Skype 서버 2019에서는 비즈니스용 Skype 서버 제어판을 사용하려면 먼저 Silverlight를 Silverlight 버전 5로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="06afb-133">이 토폴로지에는 이제 레거시 및 비즈니스용 Skype 서버 2019 서버 역할이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="06afb-134">레거시 토폴로지 작성기에서 토폴로지 열지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="06afb-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="06afb-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="06afb-136">토폴로지는 비즈니스용 Skype 서버 2019 토폴로지 작성기만 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="06afb-137">비즈니스용 Skype 서버 2019 토폴로지 작성기에서 비즈니스용 Skype 서버 2019 및 레거시 설치용 풀을 만들 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06afb-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

