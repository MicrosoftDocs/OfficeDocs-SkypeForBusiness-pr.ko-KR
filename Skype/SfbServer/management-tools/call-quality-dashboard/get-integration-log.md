---
title: 통합 로그 가져오기
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 통합 로그 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832598"
---
# <a name="get-integration-log"></a><span data-ttu-id="92717-104">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="92717-104">Get Integration Log</span></span>
 
<span data-ttu-id="92717-105">**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 통합 로그 보기 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="92717-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="92717-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="92717-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="92717-107">통합 로그 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="92717-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="92717-108">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="92717-108">Get Integration Log</span></span>

<span data-ttu-id="92717-109">통합 로그 작업에서는 QoE 큐브 처리의 작업을 설명하는 로그 항목 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="92717-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="92717-110">보안상의 이유로 이 작업은 기본적으로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92717-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="92717-111">이 설정을 사용하지 않도록 설정하면 빈 문자열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="92717-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="92717-112">이 작업을 사용하도록 설정하려면 관리자는 데이터 API의 web.config 웹 응용 프로그램에 대한 웹 응용 프로그램을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92717-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="92717-113">메서드</span><span class="sxs-lookup"><span data-stu-id="92717-113">Method</span></span>|<span data-ttu-id="92717-114">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="92717-114">**Request URI**</span></span>|<span data-ttu-id="92717-115">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="92717-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92717-116">GET</span><span class="sxs-lookup"><span data-stu-id="92717-116">GET</span></span>  <br/> |<span data-ttu-id="92717-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="92717-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="92717-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="92717-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="92717-119">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="92717-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="92717-120">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92717-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="92717-121">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="92717-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="92717-122">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92717-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="92717-123">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="92717-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="92717-124">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="92717-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="92717-125">**응답 본문** - 다음은 로그 항목의 샘플 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="92717-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


