---
title: 비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 데이터 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '요약: 통화 품질 대시보드의 데이터 API에 대해 자세히 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571922"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="fd884-104">비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 데이터 API</span><span class="sxs-lookup"><span data-stu-id="fd884-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="fd884-105">**요약:** 통화 품질 대시보드의 데이터 API에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fd884-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="fd884-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fd884-107">데이터 API는 비즈니스용 Skype 서버용 통화 품질 대시보드에 대 한 프로그래밍 방식의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="fd884-108">통화 품질 대시보드의 데이터 API</span><span class="sxs-lookup"><span data-stu-id="fd884-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="fd884-109">데이터 API는 체감 품질 큐브에 대 한 쿼리 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="fd884-110">데이터 API는 지정 된 차원과 필터를 기반으로 집계 된 체감 품질 메트릭을 제공 하는 다차원 데이터베이스 작업을 위한 REST API입니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="fd884-111">미삭 작업은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="fd884-112">**작업**</span><span class="sxs-lookup"><span data-stu-id="fd884-112">**Operation**</span></span>|<span data-ttu-id="fd884-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="fd884-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fd884-114">큐브 가져오기</span><span class="sxs-lookup"><span data-stu-id="fd884-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="fd884-115">사용 가능한 차원과 측정값의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="fd884-116">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="fd884-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="fd884-117">차원 구성원 가져오기 작업은 특정 차원의 구성원 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="fd884-118">또한 구성원 목록을 필터링 하 고 하위 집합을 가져오는 기능을 제공 하 여 회선 전송 비용을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="fd884-119">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="fd884-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="fd884-120">쿼리 실행 작업은 지정 된 차원, 측정값, 필터에 따라 큐브에 대 한 쿼리를 실행 하 고 데이터를 다시 반환할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="fd884-121">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="fd884-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="fd884-122">캐시 지우기 작업은 쿼리 및 데이터에 대 한 서버의 캐시를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="fd884-123">이렇게 하면 캐시가 다시 설정 되 고 나중에 새 요청에 대 한 체감 품질 큐브에 대 한 최신 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="fd884-124">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="fd884-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="fd884-125">통합 로그 가져오기 작업 체감 품질 큐브 처리에서 작업을 설명 하는 로그 항목의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="fd884-126">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="fd884-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="fd884-127">큐브에서 마지막 통합 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="fd884-128">**데이터 API에 대 한 CORS (교차 원본 리소스 공유) 지원**</span><span class="sxs-lookup"><span data-stu-id="fd884-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="fd884-129">데이터 API는 교차 원본 리소스 공유 (CORS)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="fd884-130">CORS는 한 도메인에서 실행 되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="fd884-131">웹 브라우저는 [같은 원본 정책](https://www.w3.org/Security/wiki/Same_Origin_Policy) 같은 원본 정책 이라고 하는 보안 제한을 구현 하 여 웹 페이지에서 다른 도메인의 api를 호출 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="fd884-132">CORS는 한 도메인 (원본 도메인)이 다른 도메인의 Api를 호출할 수 있는 안전한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="fd884-133">CORS에 대 한 자세한 내용은 [cors 사양을](https://www.w3.org/TR/cors/) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd884-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="fd884-134">**Data API 용 CORS 사용**</span><span class="sxs-lookup"><span data-stu-id="fd884-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="fd884-135">다음은 corsTrustedOrigin 응용 프로그램 설정에 나열 된 두 개의 도메인을 보여 주는 데이터 API web.config의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="fd884-136">이러한 서버에서 로드 된 스크립트에의 한 모든 요청은 Data API에서 신뢰 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="fd884-137">정확한 프로토콜, 호스트 이름 및 포트 (있는 경우)를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="fd884-138">슬래시 문자 (/)를 끝에 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fd884-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="fd884-139">여러 항목을 쉼표로 구분 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd884-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


