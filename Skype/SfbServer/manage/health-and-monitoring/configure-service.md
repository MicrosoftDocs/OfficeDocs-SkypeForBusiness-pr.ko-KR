---
title: 비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '요약: 비즈니스용 Skype 서버의 모바일 서비스에 대해 자세히 알아보세요.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818058"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="c28a7-103">비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="c28a7-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="c28a7-104">**요약:** 비즈니스용 Skype 서버의 모바일 서비스에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c28a7-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c28a7-105">이 항목은 비즈니스용 Skype Server Mobility Service (Mcx)에만 적용 되며 Lync Server 2013의 누적 업데이트에서 제공 되는 통합 커뮤니케이션 웹 API (c 2:2013)에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="c28a7-106">IIS (인터넷 정보 서비스) 7.5에서 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="c28a7-107">이동성에 IIS 7.5를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="c28a7-108">설정은 최대 동시 사용자 요청 수와 모바일 서비스에 허용 되는 최대 스레드 수에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="c28a7-109">다음은 성능 설정에 대 한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="c28a7-110">IIS 7.5에서 Mcx에 대 한 설정</span><span class="sxs-lookup"><span data-stu-id="c28a7-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="c28a7-111">**maxConcurrentThreadsPerCPU** 가 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="c28a7-112">**maxConcurrentRequestsPerCPU** 가 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="c28a7-113">ASP.NET 프로세스 모델이 AutoConfig로 설정 됩니다 (IIS 7.5에만 해당).</span><span class="sxs-lookup"><span data-stu-id="c28a7-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="c28a7-114">Http.sys 큐 한도가 1000 (기본적으로)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c28a7-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

