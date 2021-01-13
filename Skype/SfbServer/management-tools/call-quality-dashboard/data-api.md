---
title: 비즈니스용 Skype 서버의 CQD(통화 품질 대시보드)에 대한 데이터 API
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
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '요약: 통화 품질 대시보드용 데이터 API에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832698"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="9046b-104">비즈니스용 Skype 서버의 CQD(통화 품질 대시보드)에 대한 데이터 API</span><span class="sxs-lookup"><span data-stu-id="9046b-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="9046b-105">**요약:** 통화 품질 대시보드용 데이터 API에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9046b-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9046b-107">데이터 API는 비즈니스용 Skype 서버의 통화 품질 대시보드에 프로그래밍식 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="9046b-108">통화 품질 대시보드용 데이터 API</span><span class="sxs-lookup"><span data-stu-id="9046b-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="9046b-109">데이터 API는 QoE 큐브에 대한 쿼리 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="9046b-110">데이터 API는 지정된 차원 및 필터를 기반으로 집계된 QoE 메트릭을 제공하는 다차원 데이터베이스 작업을 위한 REST API입니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="9046b-111">REST 작업은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="9046b-112">**작업**</span><span class="sxs-lookup"><span data-stu-id="9046b-112">**Operation**</span></span>|<span data-ttu-id="9046b-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="9046b-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9046b-114">큐브 가져오기</span><span class="sxs-lookup"><span data-stu-id="9046b-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="9046b-115">사용 가능한 크기 및 측정값 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="9046b-116">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="9046b-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="9046b-117">차원 구성원 작업에서 특정 차원의 구성원 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="9046b-118">또한 구성원 목록을 필터링하고 하위 집합을 얻을 수 있는 기능을 제공하여 전신 전송 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="9046b-119">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="9046b-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="9046b-120">쿼리 실행 작업은 지정된 차원, 측정값 및 필터를 기반으로 큐브에서 쿼리를 실행하고 데이터를 반환하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="9046b-121">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="9046b-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="9046b-122">캐시 지우기 작업을 수행하면 쿼리 및 데이터에 대한 서버의 캐시가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="9046b-123">이렇게 하면 캐시가 다시 설정됩니다. 그러면 이후에 QoE 큐브에서 새 요청에 대한 새 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="9046b-124">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="9046b-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="9046b-125">통합 로그 작업에서는 QoE 큐브 처리의 작업을 설명하는 로그 항목 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="9046b-126">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="9046b-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="9046b-127">큐브에서 마지막 통합 데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="9046b-128">**데이터 API에 대한 CORS(원본 간 리소스 공유) 지원**</span><span class="sxs-lookup"><span data-stu-id="9046b-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="9046b-129">데이터 API는 CORS(Origin Cross-Origin Resource Sharing)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="9046b-130">CORS는 한 도메인에서 실행되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="9046b-131">웹 브라우저는 웹 페이지가 [](https://www.w3.org/Security/wiki/Same_Origin_Policy) 다른 도메인의 API를 호출하지 못하게 하는 동일한 원본 정책과 동일한 원본 정책으로 알려진 보안 제한을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="9046b-132">CORS는 한 도메인(원본 도메인)이 다른 도메인의 API를 호출할 수 있도록 안전한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="9046b-133">[CORS에 대한](https://www.w3.org/TR/cors/) 자세한 내용은 CORS 사양을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="9046b-134">**데이터 API에 CORS 사용**</span><span class="sxs-lookup"><span data-stu-id="9046b-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="9046b-135">다음은 corsTrustedOrigin 응용 프로그램 web.config 두 개의 도메인을 보여 주며 데이터 API 응용 프로그램의 발췌입니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="9046b-136">이러한 서버에서 로드된 스크립트가 요청하는 모든 요청은 데이터 API에서 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="9046b-137">정확한 프로토콜, 호스트 이름 및 포트(있는 경우)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="9046b-138">슬래시 문자(/)를 끝에 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="9046b-139">항목을 여러 개 지정하는 경우 각 항목을 콤보로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9046b-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


