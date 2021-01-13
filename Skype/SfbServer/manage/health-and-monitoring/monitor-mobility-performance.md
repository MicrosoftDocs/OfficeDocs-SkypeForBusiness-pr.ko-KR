---
title: 비즈니스용 Skype 서버에서 모바일 성능 모니터링
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '요약: 비즈니스용 Skype 서버의 Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816838"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="6fe74-103">비즈니스용 Skype 서버의 모바일 성능 모니터링</span><span class="sxs-lookup"><span data-stu-id="6fe74-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="6fe74-104">**요약:** 비즈니스용 Skype 서버의 Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="6fe74-105">비즈니스용 Skype 서버 모바일 서비스(Mcx) 및 UCWA(Unified Communications Web API)를 통해 프런트 엔드 서버 및 프런트 엔드 풀의 부하가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="6fe74-106">모바일 응용 프로그램이 최소화된 경우에도 서버에 대한 연결을 유지하는 모바일 장치(예: Lync 2010 Mobile을 실행하는 Android 및 Nokia 장치 및 Lync 2013 Mobile을 실행하는 Android 및 Apple 장치)는 모바일 응용 프로그램이 최소화될 때 서버에 대한 연결을 종료하는 장치보다 더 큰 부하를 가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="6fe74-107">모바일 사용이 증가하면 모바일 성능을 모니터링하여 용량을 늘러야 하는 경우를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="6fe74-108">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6fe74-109">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6fe74-110">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="6fe74-111">다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="6fe74-112">사용 가능한 메모리</span><span class="sxs-lookup"><span data-stu-id="6fe74-112">Available memory</span></span>
    
- <span data-ttu-id="6fe74-113">요청 큐 제한</span><span class="sxs-lookup"><span data-stu-id="6fe74-113">Request queue limit</span></span>
    
- <span data-ttu-id="6fe74-114">동시 연결 수</span><span class="sxs-lookup"><span data-stu-id="6fe74-114">Concurrent connections</span></span>
    
- <span data-ttu-id="6fe74-115">IIS 큐 길이</span><span class="sxs-lookup"><span data-stu-id="6fe74-115">IIS queue length</span></span>
    
<span data-ttu-id="6fe74-116">모바일 성능에 영향을 줄 수 있는 서버에 대한 기타 제한은 최대 12개 동시 로그인, 인증, 세션 갱신 및 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="6fe74-117">대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe74-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6fe74-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6fe74-118">In this section</span></span>

- [<span data-ttu-id="6fe74-119">비즈니스용 Skype 서버에서 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="6fe74-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="6fe74-120">비즈니스용 Skype 서버에서 Mobility Service 및 UCWA 사용 모니터링</span><span class="sxs-lookup"><span data-stu-id="6fe74-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="6fe74-121">비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="6fe74-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="6fe74-122">비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="6fe74-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="6fe74-123">비즈니스용 Skype 서버의 모바일 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="6fe74-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

