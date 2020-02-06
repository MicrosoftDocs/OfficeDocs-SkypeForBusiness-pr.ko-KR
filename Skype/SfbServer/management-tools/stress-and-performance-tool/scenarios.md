---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015를 구성 하기 위해 수행 해야 하는 작업입니다.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803878"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d3844-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오</span><span class="sxs-lookup"><span data-stu-id="d3844-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d3844-104">스트레스 및 성능 도구를 사용 하 여 성능 및 부하 테스트를 수행 하기 위해 비즈니스용 Skype 서버 2015를 구성 하기 위해 수행 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="d3844-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 (L보완 Cperftool)를 실행 하려면 비즈니스용 Skype 서버 2015 토폴로지가 사용자와 관련 된 시나리오를 위해 먼저 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="d3844-106">비즈니스용 Skype 서버 2015이 구성 되지 않았거나 올바르게 구성 되어 있지 않은 경우 부하 시뮬레이션이 실패할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="d3844-107">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용 하는 경우 [도구 다운로드](https://www.microsoft.com/download/details.aspx?id=50367)의 일부로 비즈니스용 Skype 서버 관리 셸 스크립트와 기본 리소스 파일에 대 한 예를 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="d3844-108">이는 비즈니스용 Skype 서버 배포를 구성 하는 출발점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="d3844-109">이 문서에서는 제공 되는 Windows PowerShell 예제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3844-110">이 항목에서는 비즈니스용 Skype Server 2015를 구성 하는 방법을 설명 하는 데 도움이 되지 않습니다 .이에 대 한 다른 계획 및 배포 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="d3844-111">비즈니스용 Skype 서버 2015에서 Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은 여기 소개의 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3844-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="d3844-112">비즈니스용 Skype 서버 관리 셸 스크립트를 실행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d3844-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="d3844-113">부하 시뮬레이션을 준비 하는 데 사용할 수 있는 샘플 PowerShell 스크립트를 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="d3844-114">이러한 스크립트는 부하 시뮬레이션을 위한 것 이므로 간단 하 고 관대 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="d3844-115">이는 프로덕션 환경에 적합 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="d3844-116">이번에도 이러한 스크립트는 샘플 이므로이를 검토 해야 하며, 대부분의 경우 해당 작업을 효율적으로 사용할 수 있도록 하기 전에 사용자의 환경과 관련 된 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="d3844-117">최소한, 상담원에 게 할당 된 에이전트를 지정 하려면 토폴로지가 염두에 있는 RSG (응답 서비스 그룹) 스크립트를 수정 해야 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="d3844-118">하지만 필요 하지 않은 경우에는이를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d3844-119">이러한 샘플을 검토 하 고 이해 하는 데 주의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3844-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="d3844-120">스크립트를 실행 하면 토폴로지의 기존 설정이 덮어쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="d3844-121">스트레스 및 성능 도구 클라이언트 버전 이름</span><span class="sxs-lookup"><span data-stu-id="d3844-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="d3844-122">이전에 기본값의 설정을 변경한 경우 클라이언트 버전 검사 정책을 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="d3844-123">이에 대해 잘 모르는 경우 [클라이언트 버전 검사 설명서](https://msdn.microsoft.com/en-us/vsto/jj923060)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3844-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="d3844-124">스트레스 및 성능 도구는 비즈니스용 Skype 서버 2015와 통신할 때 기본적으로 다음 사용자 에이전트 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="d3844-125">LSPT/15.0.0.0 (비즈니스용 Skype Server 2015 스트레스 및 성능 도구)</span><span class="sxs-lookup"><span data-stu-id="d3844-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="d3844-126">OCPHONE/0.522</span><span class="sxs-lookup"><span data-stu-id="d3844-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="d3844-127">L Ccptool의 Mobility (모바일) 클라이언트에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3844-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="d3844-128">도구/웹 회의</span><span class="sxs-lookup"><span data-stu-id="d3844-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="d3844-129">도구/모바일</span><span class="sxs-lookup"><span data-stu-id="d3844-129">UCWA Perf Tool/Mobile</span></span>
    

