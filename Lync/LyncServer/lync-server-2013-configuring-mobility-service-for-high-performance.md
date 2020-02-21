---
title: 'Lync Server 2013: 고성능을 위한 모바일 서비스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35d45c1b437c04e96885f098df6026650d61768
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="23dca-102">Lync Server 2013에서 고성능을 위한 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="23dca-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23dca-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="23dca-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="23dca-104">이 항목은 Lync server 2013 Mobility Service (Mcx)에만 적용 되며 Lync Server 2013에 대 한 누적 업데이트: 2 월 2013에 제공 되는 통합 커뮤니케이션 웹 API (WA)에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="23dca-105">IIS (인터넷 정보 서비스) 7.5에 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="23dca-106">모바일 기능에는 IIS 7.5를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="23dca-107">이러한 설정은 최대 동시 사용자 요청 수 및 Mobility Service에 대해 허용되는 최대 스레드 수에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="23dca-108">다음은 성능 설정에 대 한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="23dca-109">IIS 7.5의 Mcx에 대 한 설정</span><span class="sxs-lookup"><span data-stu-id="23dca-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="23dca-110">**maxConcurrentThreadsPerCPU**는 영(0)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="23dca-111">**maxConcurrentRequestsPerCPU**는 영(0)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="23dca-112">ASP.NET 프로세스 모델은 AutoConfig로 설정됩니다(IIS 7.5에만 해당).</span><span class="sxs-lookup"><span data-stu-id="23dca-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="23dca-113">HTTP.sys 큐 제한은 기본적으로 1,000으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23dca-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

