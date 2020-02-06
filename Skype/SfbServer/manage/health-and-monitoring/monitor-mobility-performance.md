---
title: 비즈니스용 Skype 서버에서 성능에 대 한 이동성 모니터링
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '요약: 비즈니스용 Skype 서버의 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 대해 알아봅니다.'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817837"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="8dfb3-103">비즈니스용 Skype 서버에서 성능에 대 한 이동성 모니터링</span><span class="sxs-lookup"><span data-stu-id="8dfb3-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="8dfb3-104">**요약:** 비즈니스용 Skype 서버의 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="8dfb3-105">비즈니스용 Skype Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)는 프런트 엔드 서버 및 프런트 엔드 풀의 로드를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="8dfb3-106">Lync 및 lync 2013 Mobile을 실행 하는 android 및 Apple 장치는 물론 모바일 응용 프로그램이 2010 최소화 되는 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 장치 보다 더 많은 부하를 할 수 있습니다. 모바일 응용 프로그램이 최소화 된 상태에서 서버에 대 한 연결을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="8dfb3-107">이동성 사용량이 증가 함에 따라 이동성 성능을 모니터링 하 여 용량을 늘려야 할 시기를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="8dfb3-108">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8dfb3-109">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8dfb3-110">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="8dfb3-111">이동성 성능에 영향을 주는 몇 가지 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="8dfb3-112">사용 가능한 메모리</span><span class="sxs-lookup"><span data-stu-id="8dfb3-112">Available memory</span></span>
    
- <span data-ttu-id="8dfb3-113">요청 큐 제한</span><span class="sxs-lookup"><span data-stu-id="8dfb3-113">Request queue limit</span></span>
    
- <span data-ttu-id="8dfb3-114">동시 연결</span><span class="sxs-lookup"><span data-stu-id="8dfb3-114">Concurrent connections</span></span>
    
- <span data-ttu-id="8dfb3-115">IIS 대기열 길이</span><span class="sxs-lookup"><span data-stu-id="8dfb3-115">IIS queue length</span></span>
    
<span data-ttu-id="8dfb3-116">이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="8dfb3-117">대부분의 배포의 경우 이러한 최대값을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb3-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8dfb3-118">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="8dfb3-118">In this section</span></span>

- [<span data-ttu-id="8dfb3-119">비즈니스용 Skype 서버에서 서버 메모리 용량 한도 모니터링</span><span class="sxs-lookup"><span data-stu-id="8dfb3-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="8dfb3-120">비즈니스용 Skype 서버에서 이동성 서비스 및 함께 사용 모니터링</span><span class="sxs-lookup"><span data-stu-id="8dfb3-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="8dfb3-121">비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="8dfb3-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="8dfb3-122">비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="8dfb3-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="8dfb3-123">비즈니스용 Skype 서버의 이동성 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="8dfb3-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

