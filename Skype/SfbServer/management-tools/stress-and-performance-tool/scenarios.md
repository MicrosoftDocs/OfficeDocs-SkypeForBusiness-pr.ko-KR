---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 스트레스 및 성능 도구를 사용하여 성능 및 부하 테스트를 수행하도록 비즈니스용 Skype 서버 2015를 구성하는 데 필요한 작업입니다.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105374"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="7c8e9-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오</span><span class="sxs-lookup"><span data-stu-id="7c8e9-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="7c8e9-104">스트레스 및 성능 도구를 사용하여 성능 및 부하 테스트를 수행하도록 비즈니스용 Skype 서버 2015를 구성하는 데 필요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="7c8e9-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구(LyncPerfTool)를 실행하려면 먼저 비즈니스용 Skype 서버 2015 토폴로지가 사용자와 관련된 시나리오에 맞게 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="7c8e9-106">비즈니스용 Skype 서버 2015가 구성되지 않거나 잘못 구성된 경우 부하 시뮬레이션이 실패할 가능성이 매우 높습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="7c8e9-107">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용하여 도구 다운로드의 일부로 예제 비즈니스용 Skype 서버 관리 셸 스크립트 및 기본 리소스 [파일을 제공합니다.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="7c8e9-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="7c8e9-108">이러한 구성은 비즈니스용 Skype 서버 배포를 구성하기 위한 시작 지점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="7c8e9-109">이 문서에서는 제공된 Windows PowerShell 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c8e9-110">이 항목은 일반적으로 비즈니스용 Skype 서버 2015를 구성하는 방법을 설명하는 데 도움이되지 않습니다. 이에 대한 다른 계획 및 배포 항목도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="7c8e9-111">비즈니스용 Skype 서버 2015에서 Windows PowerShell 대한 자세한 내용은 Insert introduction HERE에서 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="7c8e9-112">비즈니스용 Skype 서버 관리 셸 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="7c8e9-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="7c8e9-113">부하 시뮬레이션을 준비하는 데 사용할 수 있는 샘플 PowerShell 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="7c8e9-114">이러한 스크립트는 로드 시뮬레이션을 위한 것이기 때문에 간단하고 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="7c8e9-115">이는 프로덕션 환경에 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="7c8e9-116">다시 한 번 이러한 스크립트는 샘플이며, 이를 검토해야 함을 강조하고, 대부분의 경우 실제적으로 사용하기 전에 사용자 환경과 관련된 변경을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="7c8e9-117">최소한 토폴로지와 함께 RSG(응답 서비스 그룹) 스크립트를 수정해야 합니다(에이전트 그룹에 할당된 에이전트를 지정).</span><span class="sxs-lookup"><span data-stu-id="7c8e9-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="7c8e9-118">그러나 필요하지 않은 경우 실행할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7c8e9-119">이러한 샘플을 검토하고 이해하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="7c8e9-120">스크립트는 실행 시 토폴로지의 기존 설정을 덮어 덮어 덮어 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="7c8e9-121">스트레스 및 성능 도구 클라이언트 버전 이름</span><span class="sxs-lookup"><span data-stu-id="7c8e9-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="7c8e9-122">이전에 설정을 기본값에서 변경한 경우 클라이언트 버전 확인 정책을 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="7c8e9-123">이 문제가 없는 경우 클라이언트 버전 확인 [설명서를 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)</span><span class="sxs-lookup"><span data-stu-id="7c8e9-123">If you're unsure about this, check the [Client Version Check documentation](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).</span></span>
  
<span data-ttu-id="7c8e9-124">스트레스 및 성능 도구는 비즈니스용 Skype 서버 2015와 통신할 때 기본적으로 다음 사용자 에이전트 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="7c8e9-125">LSPT/15.0.0.0(비즈니스용 Skype 서버 2015 스트레스 및 성능 도구)</span><span class="sxs-lookup"><span data-stu-id="7c8e9-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="7c8e9-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="7c8e9-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="7c8e9-127">LyncPerfTool의 UCWA(Mobility) 클라이언트의 경우:</span><span class="sxs-lookup"><span data-stu-id="7c8e9-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="7c8e9-128">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="7c8e9-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="7c8e9-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="7c8e9-129">UCWA Perf Tool/Mobile</span></span>
