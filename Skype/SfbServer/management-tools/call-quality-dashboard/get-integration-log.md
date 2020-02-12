---
title: 통합 로그 가져오기
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 통합 로그 가져오기 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888807"
---
# <a name="get-integration-log"></a><span data-ttu-id="b58cd-104">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="b58cd-104">Get Integration Log</span></span>
 
<span data-ttu-id="b58cd-105">**요약:** 통화 품질 대시보드의 데이터 API에 포함 된 통합 로그 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b58cd-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b58cd-107">통합 로그 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="b58cd-108">통합 로그 가져오기</span><span class="sxs-lookup"><span data-stu-id="b58cd-108">Get Integration Log</span></span>

<span data-ttu-id="b58cd-109">통합 로그 가져오기 작업 체감 품질 큐브 처리에서 작업을 설명 하는 로그 항목의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="b58cd-110">이 작업은 보안상의 이유로 기본적으로 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="b58cd-111">이 기능을 사용 하지 않도록 설정 하면 빈 문자열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="b58cd-112">이 작업을 사용 하도록 설정 하려면 관리자가 Data API의 호스트 웹 응용 프로그램에 대 한 web.config를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="b58cd-113">메서드와</span><span class="sxs-lookup"><span data-stu-id="b58cd-113">Method</span></span>|<span data-ttu-id="b58cd-114">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="b58cd-114">**Request URI**</span></span>|<span data-ttu-id="b58cd-115">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="b58cd-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b58cd-116">가져오기</span><span class="sxs-lookup"><span data-stu-id="b58cd-116">GET</span></span>  <br/> |<span data-ttu-id="b58cd-117">https://\<포털\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="b58cd-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="b58cd-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b58cd-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b58cd-119">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="b58cd-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b58cd-120">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b58cd-121">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="b58cd-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b58cd-122">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b58cd-123">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b58cd-124">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b58cd-125">**응답 본문** -아래에는 로그 항목의 샘플 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b58cd-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


