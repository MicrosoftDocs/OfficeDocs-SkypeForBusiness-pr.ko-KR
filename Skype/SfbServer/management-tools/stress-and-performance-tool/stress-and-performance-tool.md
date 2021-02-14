---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션 환경이나 테스트 환경이 아닌 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814928"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ec6f9-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="ec6f9-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ec6f9-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션 환경이나 테스트 환경이 아닌 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="ec6f9-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 비즈니스용 Skype 서버 2015의 용량 계획을 간소화하는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="ec6f9-106">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="ec6f9-107">비즈니스용 Skype 서버에 대한 하드웨어 계획 간소화</span><span class="sxs-lookup"><span data-stu-id="ec6f9-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="ec6f9-108">성능 조정을 위한 더 많은 지식과 모범 사례 제공</span><span class="sxs-lookup"><span data-stu-id="ec6f9-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="ec6f9-109">비즈니스용 Skype 서버 배포의 성능 측정</span><span class="sxs-lookup"><span data-stu-id="ec6f9-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="ec6f9-110">일반적으로 비즈니스용 [Skype 서버 2015](../../management-tools/planning-tool/planning-tool.md) 계획 도구를 사용하여 토폴로지 디자인 및 비즈니스용 Skype [서버 2015](../../management-tools/capacity-planning-calculator.md)용량 계획 계산기를 사용하여 토폴로지 구체화한 후에 이 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="ec6f9-111">이 도구는 비즈니스용 Skype 서버 2019에 대해 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="ec6f9-112">테스트</span><span class="sxs-lookup"><span data-stu-id="ec6f9-112">Tests</span></span>

<span data-ttu-id="ec6f9-113">스트레스 및 성능 도구는 다음 유형의 사용자 부하를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ec6f9-114">IM(인스턴트 메시징) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="ec6f9-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="ec6f9-115">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="ec6f9-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="ec6f9-116">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="ec6f9-116">Application sharing</span></span>  <br/> |<span data-ttu-id="ec6f9-117">PTSN(Public Switched Telephone Network) 시뮬레이션을 포함한 VoIP(Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="ec6f9-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="ec6f9-118">웹 액세스 클라이언트 회의</span><span class="sxs-lookup"><span data-stu-id="ec6f9-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="ec6f9-119">회의 자동 회의</span><span class="sxs-lookup"><span data-stu-id="ec6f9-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="ec6f9-120">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="ec6f9-120">Response Groups</span></span>  <br/> |<span data-ttu-id="ec6f9-121">메일 목록 확장</span><span class="sxs-lookup"><span data-stu-id="ec6f9-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="ec6f9-122">주소부 다운로드 및 주소부 쿼리</span><span class="sxs-lookup"><span data-stu-id="ec6f9-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="ec6f9-123">E911(Enhanced 911) 통화 및 위치 프로필(다이얼 플랜)</span><span class="sxs-lookup"><span data-stu-id="ec6f9-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="ec6f9-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="ec6f9-124">MultiView</span></span>  <br/> |<span data-ttu-id="ec6f9-125">데이터 공동 작업</span><span class="sxs-lookup"><span data-stu-id="ec6f9-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="ec6f9-126">이동성</span><span class="sxs-lookup"><span data-stu-id="ec6f9-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ec6f9-127">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 포함된 응용 프로그램 및 파일</span><span class="sxs-lookup"><span data-stu-id="ec6f9-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="ec6f9-128">이러한 응용 프로그램은 비즈니스용 Skype 서버 스트레스 및 성능 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="ec6f9-129">**도구**</span><span class="sxs-lookup"><span data-stu-id="ec6f9-129">**Tool**</span></span>|<span data-ttu-id="ec6f9-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="ec6f9-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec6f9-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="ec6f9-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="ec6f9-132">이 도구는 사용자 및 연락처를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="ec6f9-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="ec6f9-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="ec6f9-134">시뮬레이션할 사용자 부하의 특성을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="ec6f9-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="ec6f9-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="ec6f9-136">사용자 부하를 시뮬레이트하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="ec6f9-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="ec6f9-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="ec6f9-138">비즈니스용 Skype 서버 2015 로깅 도구를 사용하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="ec6f9-139">프로비전 스크립트 예제</span><span class="sxs-lookup"><span data-stu-id="ec6f9-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="ec6f9-140">특정 시나리오에 따라 부하 테스트를 실행하도록 토폴로지 구성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="ec6f9-141">특정 환경과 관련이 있도록 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="ec6f9-142">이 섹션의 항목</span><span class="sxs-lookup"><span data-stu-id="ec6f9-142">Topics in this section</span></span>

<span data-ttu-id="ec6f9-143">자세한 내용은 다음 문서를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6f9-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="ec6f9-144">Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정</span><span class="sxs-lookup"><span data-stu-id="ec6f9-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="ec6f9-145">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오</span><span class="sxs-lookup"><span data-stu-id="ec6f9-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="ec6f9-146">스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전</span><span class="sxs-lookup"><span data-stu-id="ec6f9-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="ec6f9-147">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ec6f9-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="ec6f9-148">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용</span><span class="sxs-lookup"><span data-stu-id="ec6f9-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="ec6f9-149">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="ec6f9-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

