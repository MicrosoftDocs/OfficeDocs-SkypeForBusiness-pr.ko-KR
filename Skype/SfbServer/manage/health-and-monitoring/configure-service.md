---
title: 비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '요약: 비즈니스용 Skype 서버의 Mobility Service에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817038"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="eb10c-103">비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="eb10c-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="eb10c-104">**요약:** 비즈니스용 Skype 서버의 Mobility Service에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eb10c-105">이 항목은 비즈니스용 Skype 서버 Mobility Service(Mcx)에만 적용되고 Lync Server 2013: 2013년 2월 누적 업데이트에 제공된 UCWA(Unified Communications Web API)에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="eb10c-106">IIS(인터넷 정보 서비스) 7.5에 Mcx(Mobility Service)를 설치하면 Mobility Service 설치 관리자에서 프런트 엔드 서버에서 일부 성능 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="eb10c-107">모바일 기능에는 IIS 7.5를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="eb10c-108">이러한 설정은 최대 동시 사용자 요청 수 및 Mobility Service에 대해 허용되는 최대 스레드 수에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="eb10c-109">성능 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="eb10c-110">IIS 7.5의 Mcx 설정</span><span class="sxs-lookup"><span data-stu-id="eb10c-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="eb10c-111">**maxConcurrentThreadsPerCPU** 는 영(0)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="eb10c-112">**maxConcurrentRequestsPerCPU** 는 영(0)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="eb10c-113">ASP.NET 프로세스 모델은 AutoConfig로 설정됩니다(IIS 7.5에만 해당).</span><span class="sxs-lookup"><span data-stu-id="eb10c-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="eb10c-114">HTTP.sys 큐 제한은 기본적으로 1,000으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb10c-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

