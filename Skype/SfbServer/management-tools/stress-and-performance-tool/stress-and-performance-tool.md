---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션이 아닌 환경이 나 테스트 환경에서 용량 계획과 성능 조정 중에 사용 됩니다.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816157"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d6f2c-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="d6f2c-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d6f2c-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션이 아닌 환경이 나 테스트 환경에서 용량 계획과 성능 조정 중에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="d6f2c-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 비즈니스용 Skype Server 2015에 대 한 용량 계획을 간소화 하는 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="d6f2c-106">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 다음을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="d6f2c-107">비즈니스용 Skype 서버에 대 한 하드웨어 계획 간소화</span><span class="sxs-lookup"><span data-stu-id="d6f2c-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="d6f2c-108">향상 된 성능 조정에 대 한 지식 및 모범 사례 제공</span><span class="sxs-lookup"><span data-stu-id="d6f2c-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="d6f2c-109">비즈니스용 Skype 서버 배포의 성과 측정</span><span class="sxs-lookup"><span data-stu-id="d6f2c-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="d6f2c-110">일반적으로이 도구는 비즈니스용 [Skype 서버 2015 계획 도구](../../management-tools/planning-tool/planning-tool.md) 를 사용 하 여 토폴로지를 디자인 하 고 [비즈니스용 Skype Server 2015 용량 계획 계산기](../../management-tools/capacity-planning-calculator.md)를 사용 하 여 토폴로지를 구체화 한 후에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="d6f2c-111">이 도구는 비즈니스용 Skype 서버 2019 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="d6f2c-112">테스트</span><span class="sxs-lookup"><span data-stu-id="d6f2c-112">Tests</span></span>

<span data-ttu-id="d6f2c-113">스트레스 및 성능 도구를 사용 하 여 이러한 유형의 사용자 부하를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d6f2c-114">인스턴트 메시지 (IM) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="d6f2c-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="d6f2c-115">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="d6f2c-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="d6f2c-116">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d6f2c-116">Application sharing</span></span>  <br/> |<span data-ttu-id="d6f2c-117">PTSN (공개 통신 네트워크) 시뮬레이션을 포함 한 VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="d6f2c-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="d6f2c-118">웹 액세스 클라이언트 회의</span><span class="sxs-lookup"><span data-stu-id="d6f2c-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="d6f2c-119">회의 자동 전화 교환</span><span class="sxs-lookup"><span data-stu-id="d6f2c-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="d6f2c-120">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="d6f2c-120">Response Groups</span></span>  <br/> |<span data-ttu-id="d6f2c-121">메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="d6f2c-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="d6f2c-122">주소록 다운로드 및 주소록 쿼리</span><span class="sxs-lookup"><span data-stu-id="d6f2c-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="d6f2c-123">향상 된 911 (E911) 통화 및 위치 프로필 (다이얼 플랜)</span><span class="sxs-lookup"><span data-stu-id="d6f2c-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="d6f2c-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="d6f2c-124">MultiView</span></span>  <br/> |<span data-ttu-id="d6f2c-125">데이터 공동 작업</span><span class="sxs-lookup"><span data-stu-id="d6f2c-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="d6f2c-126">이동성</span><span class="sxs-lookup"><span data-stu-id="d6f2c-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d6f2c-127">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 포함 된 응용 프로그램 및 파일</span><span class="sxs-lookup"><span data-stu-id="d6f2c-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="d6f2c-128">이러한 응용 프로그램은 비즈니스용 Skype 서버 스트레스 및 성능 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="d6f2c-129">**도구**</span><span class="sxs-lookup"><span data-stu-id="d6f2c-129">**Tool**</span></span>|<span data-ttu-id="d6f2c-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="d6f2c-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6f2c-131">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="d6f2c-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="d6f2c-132">이 도구는 사용자 및 연락처를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="d6f2c-133">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="d6f2c-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="d6f2c-134">시뮬레이트 하는 사용자 부하의 특성을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="d6f2c-135">L Cperftool .exe</span><span class="sxs-lookup"><span data-stu-id="d6f2c-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="d6f2c-136">사용자 부하를 시뮬레이트하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="d6f2c-137">Default. tmx</span><span class="sxs-lookup"><span data-stu-id="d6f2c-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="d6f2c-138">비즈니스용 Skype 서버 2015 로깅 도구를 사용 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="d6f2c-139">프로비저닝 스크립트 예제</span><span class="sxs-lookup"><span data-stu-id="d6f2c-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="d6f2c-140">특정 시나리오에 따라 부하 테스트 실행에 대 한 토폴로지를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="d6f2c-141">특정 환경과 관련 되도록 수정 해야 할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="d6f2c-142">이 섹션의 항목</span><span class="sxs-lookup"><span data-stu-id="d6f2c-142">Topics in this section</span></span>

<span data-ttu-id="d6f2c-143">자세한 정보를 알고 싶은 경우 다음 문서를 검토 하셔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6f2c-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="d6f2c-144">명함 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정</span><span class="sxs-lookup"><span data-stu-id="d6f2c-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="d6f2c-145">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오</span><span class="sxs-lookup"><span data-stu-id="d6f2c-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="d6f2c-146">스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전</span><span class="sxs-lookup"><span data-stu-id="d6f2c-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="d6f2c-147">비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d6f2c-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="d6f2c-148">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용</span><span class="sxs-lookup"><span data-stu-id="d6f2c-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="d6f2c-149">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="d6f2c-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

