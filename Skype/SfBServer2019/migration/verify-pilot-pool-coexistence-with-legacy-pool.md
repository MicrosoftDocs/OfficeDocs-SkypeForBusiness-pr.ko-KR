---
title: 레거시 풀과의 파일럿 풀 공존 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 풀과의 파일럿 풀 공존을 확인 하는 프로세스입니다.
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "36197987"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="1081e-103">레거시 풀과의 파일럿 풀 공존 확인</span><span class="sxs-lookup"><span data-stu-id="1081e-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="1081e-104">**이 문서의 내용**</span><span class="sxs-lookup"><span data-stu-id="1081e-104">**In this article**</span></span>
  
[<span data-ttu-id="1081e-105">비즈니스용 Skype Server 2019 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="1081e-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="1081e-106">비즈니스용 Skype 서버 2019 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="1081e-107">레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함</span><span class="sxs-lookup"><span data-stu-id="1081e-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="1081e-108">파일럿 풀을 배포한 후에는 관리 도구를 사용 하 여 풀 정보를 보는 방법으로 두 풀의 공존을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="1081e-109">비즈니스용 Skype 서버 2019 풀 및 레거시 풀에는 비즈니스용 Skype Server 2019 제어판 및 토폴로지 작성기 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="1081e-110">비즈니스용 Skype Server 2019 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="1081e-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="1081e-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1081e-111"></span></span>

1. <span data-ttu-id="1081e-112">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 관리 toolservices 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="1081e-113">프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="1081e-114">중앙 로깅 서비스 에이전트</span><span class="sxs-lookup"><span data-stu-id="1081e-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="1081e-115">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="1081e-115">Application Sharing</span></span>
    - <span data-ttu-id="1081e-116">오디오 테스트 서비스</span><span class="sxs-lookup"><span data-stu-id="1081e-116">Audio Test Service</span></span>
    - <span data-ttu-id="1081e-117">오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="1081e-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="1081e-118">통화 대기</span><span class="sxs-lookup"><span data-stu-id="1081e-118">Call Park</span></span>
    - <span data-ttu-id="1081e-119">회의 알림</span><span class="sxs-lookup"><span data-stu-id="1081e-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="1081e-120">회의 전화 교환</span><span class="sxs-lookup"><span data-stu-id="1081e-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="1081e-121">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="1081e-121">Front-End</span></span>
    - <span data-ttu-id="1081e-122">메신저 대화 회의</span><span class="sxs-lookup"><span data-stu-id="1081e-122">IM Conferencing</span></span>
    - <span data-ttu-id="1081e-123">중재</span><span class="sxs-lookup"><span data-stu-id="1081e-123">Mediation</span></span>
    - <span data-ttu-id="1081e-124">복제 복제기 에이전트</span><span class="sxs-lookup"><span data-stu-id="1081e-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="1081e-125">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="1081e-125">Response Group</span></span>
    - <span data-ttu-id="1081e-126">웹 회의</span><span class="sxs-lookup"><span data-stu-id="1081e-126">Web Conferencing</span></span>
    - <span data-ttu-id="1081e-127">XMPP 번역 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="1081e-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="1081e-128">비즈니스용 Skype 서버 2019 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="1081e-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="1081e-129"></span></span>

<span data-ttu-id="1081e-130">비즈니스용 Skype Server 2019 배포의 프런트 엔드 서버에서 비즈니스용 Skype Server 2019 제어판을 열고 레거시 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="1081e-131">이 절차를 반복 하 여 비즈니스용 Skype 서버 2019 풀을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1081e-132">비즈니스용 Skype Server 2019에서 비즈니스용 Skype 서버 제어판을 사용 하기 전에 silverlight 버전 5로 Silverlight를 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="1081e-133">이 토폴로지에는 이제 레거시 및 비즈니스용 Skype 서버 2019 서버 역할이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="1081e-134">레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함</span><span class="sxs-lookup"><span data-stu-id="1081e-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="1081e-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="1081e-135"></span></span>

<span data-ttu-id="1081e-136">토폴로지는 비즈니스용 Skype 서버 2019 토폴로지 작성기를 사용해 서만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="1081e-137">비즈니스용 skype server 2019 토폴로지 작성기를 사용 하 여 비즈니스용 Skype Server 2019과 레거시 설치 모두에 대 한 풀을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1081e-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

