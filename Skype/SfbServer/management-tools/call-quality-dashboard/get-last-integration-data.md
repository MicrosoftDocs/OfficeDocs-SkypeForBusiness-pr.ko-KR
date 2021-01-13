---
title: 마지막 통합 데이터 가져오기
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 마지막 통합 데이터 얻기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832518"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="7b30f-104">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="7b30f-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="7b30f-105">**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 마지막 통합 데이터 얻기 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="7b30f-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7b30f-107">마지막 통합 데이터 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="7b30f-108">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="7b30f-108">Get Last Integration Data</span></span>

<span data-ttu-id="7b30f-109">마지막 통합 데이터 저장 작업은 보관 및 큐브 처리의 마지막 5개 성공/실패 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="7b30f-110">이 기능은 기본적으로 사용하지 않도록 설정되어 있으며 데이터 API를 구성하여 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="7b30f-111">**방법**</span><span class="sxs-lookup"><span data-stu-id="7b30f-111">**Method**</span></span>|<span data-ttu-id="7b30f-112">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="7b30f-112">**Request URI**</span></span>|<span data-ttu-id="7b30f-113">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="7b30f-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b30f-114">GET</span><span class="sxs-lookup"><span data-stu-id="7b30f-114">GET</span></span>  <br/> |<span data-ttu-id="7b30f-115">https:// \<portal\> /QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="7b30f-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="7b30f-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7b30f-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7b30f-117">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="7b30f-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7b30f-118">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b30f-119">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="7b30f-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7b30f-120">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7b30f-121">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7b30f-122">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="7b30f-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b30f-123">**응답 본문** - 다음은 샘플 로그 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7b30f-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
