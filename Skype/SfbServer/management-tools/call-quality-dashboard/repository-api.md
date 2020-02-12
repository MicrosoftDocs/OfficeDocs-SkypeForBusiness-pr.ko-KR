---
title: 비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 리포지토리 API
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
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '요약: 통화 품질 대시보드의 리포지토리 API에 대해 자세히 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888787"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="26747-104">비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 리포지토리 API</span><span class="sxs-lookup"><span data-stu-id="26747-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="26747-105">**요약:** 통화 품질 대시보드의 리포지토리 API에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="26747-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="26747-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="26747-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="26747-107">리포지토리 API는 비즈니스용 Skype 서버용 통화 품질 대시보드에 대 한 프로그래밍 방식의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="26747-108">통화 품질 대시보드의 리포지토리 API</span><span class="sxs-lookup"><span data-stu-id="26747-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="26747-109">리포지토리 API는 리포지토리 데이터베이스에 대 한 데이터 액세스 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="26747-110">저장소를 사용 하면 사용자가 사용자에 게 적합 한 방식으로 콘텐츠를 그룹화 할 수 있도록 트리나 그래프 구조로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26747-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="26747-111">리포지토리는 저장소를 나타내는 기본 제공 사용자 인 시스템 사용자와 리포지토리의 승인 된 사용자를 나타내는 일반 사용자의 두 가지 일반적인 사용자 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="26747-112">리포지토리 API는 다음과 같은 세 가지 일반 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26747-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="26747-113">[CQD-사용자에 대 한 사용자 서비스](user-service.md) .</span><span class="sxs-lookup"><span data-stu-id="26747-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="26747-114">[CQD (통화 품질 대시보드) 용 항목 서비스](item-service.md) -항목에 액세스 하 고 항목에 저장 된 내용에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="26747-115">[CQD (통화 품질 대시보드)에 대 한 사용자 설정 서비스](user-settings-service.md) -사용자 설정에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="26747-116">통화 품질 대시보드는 리포지토리 API를 사용 하 여 다음 정보를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="26747-117">**사용자** -저장소에 대 한 액세스 권한이 있는 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="26747-118">**보고서** -저장소 항목의 콘텐츠로 저장 된 쿼리 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="26747-119">**쿼리** -데이터 API에서 데이터를 검색 하는 데 사용 되며, 저장소 항목의 콘텐츠로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26747-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="26747-120">**사용자 설정** -사용자의 선택적 응용 프로그램 동작을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="26747-121">**리포지토리 API에 대 한 CORS (교차 원본 리소스 공유) 지원**</span><span class="sxs-lookup"><span data-stu-id="26747-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="26747-122">리포지토리 API는 교차 원본 리소스 공유 (CORS)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="26747-123">CORS는 한 도메인에서 실행 되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="26747-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="26747-124">웹 브라우저는 [같은 원본 정책](https://www.w3.org/Security/wiki/Same_Origin_Policy) 같은 원본 정책 이라고 하는 보안 제한을 구현 하 여 웹 페이지에서 다른 도메인의 api를 호출 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="26747-125">CORS는 한 도메인 (원본 도메인)이 다른 도메인의 Api를 호출할 수 있는 안전한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="26747-126">CORS에 대 한 자세한 내용은 [cors 사양을](https://www.w3.org/TR/cors/) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26747-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="26747-127">**리포지토리 API 용 CORS 사용**</span><span class="sxs-lookup"><span data-stu-id="26747-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="26747-128">다음은 corsTrustedOrigin 응용 프로그램 설정에 나열 된 두 개의 도메인을 보여 주는 리포지토리 API web.config의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="26747-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="26747-129">이러한 서버에서 로드 된 스크립트에의 한 모든 요청은 리포지토리 API에서 신뢰 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="26747-130">정확한 프로토콜, 호스트 이름 및 포트 (있는 경우)를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26747-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="26747-131">슬래시 문자 (/)를 끝에 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="26747-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="26747-132">여러 항목을 쉼표로 구분 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26747-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


