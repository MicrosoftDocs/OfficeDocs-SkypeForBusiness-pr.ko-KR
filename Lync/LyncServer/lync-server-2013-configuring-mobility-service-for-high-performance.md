---
title: 'Lync Server 2013: 고성능을 위한 이동성 서비스 구성'
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
ms.openlocfilehash: 29eaea1e45c5d3b745debbc2f97370a76e6d16db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="7db08-102">Lync Server 2013에서 고성능을 위한 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="7db08-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7db08-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7db08-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7db08-104">이 항목은 Lync Server 2013 Mobility Service (Mcx)에만 적용 되며 Lync Server 2013의 누적 업데이트에서 제공 되는 통합 커뮤니케이션 웹 API (c 2 월 2013)에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="7db08-105">IIS (인터넷 정보 서비스) 7.5에서 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="7db08-106">이동성에 IIS 7.5를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="7db08-107">설정은 최대 동시 사용자 요청 수와 모바일 서비스에 허용 되는 최대 스레드 수에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="7db08-108">다음은 성능 설정에 대 한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="7db08-109">IIS 7.5에서 Mcx에 대 한 설정</span><span class="sxs-lookup"><span data-stu-id="7db08-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="7db08-110">**maxConcurrentThreadsPerCPU** 가 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="7db08-111">**maxConcurrentRequestsPerCPU** 가 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="7db08-112">ASP.NET 프로세스 모델이 AutoConfig로 설정 됩니다 (IIS 7.5에만 해당).</span><span class="sxs-lookup"><span data-stu-id="7db08-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="7db08-113">Http.sys 큐 한도가 1000 (기본적으로)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7db08-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

