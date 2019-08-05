---
title: 마지막 통합 데이터 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 마지막 통합 데이터 가져오기 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: d110bdc1fe88a9fe7f77abe7f7b9ed47a3324eb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186918"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="2df35-104">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="2df35-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="2df35-105">**요약:** 통화 품질 대시보드의 데이터 API의 일부인 마지막 통합 데이터 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="2df35-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="2df35-107">마지막 통합 데이터 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="2df35-108">마지막 통합 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="2df35-108">Get Last Integration Data</span></span>

<span data-ttu-id="2df35-109">마지막 통합 데이터 가져오기 작업은 보관 및 큐브 처리의 마지막 5 개 성공/실패 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="2df35-110">이 기능은 기본적으로 사용 하지 않도록 설정 되어 있으며 데이터 API를 구성 하 여 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="2df35-111">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="2df35-111">**Method**</span></span>|<span data-ttu-id="2df35-112">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="2df35-112">**Request URI**</span></span>|<span data-ttu-id="2df35-113">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="2df35-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2df35-114">가져오기</span><span class="sxs-lookup"><span data-stu-id="2df35-114">GET</span></span>  <br/> |<span data-ttu-id="2df35-115">https://\<포털\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="2df35-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="2df35-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="2df35-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="2df35-117">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="2df35-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="2df35-118">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2df35-119">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="2df35-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="2df35-120">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="2df35-121">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="2df35-122">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2df35-123">**응답 본문** -아래는 예제 로그 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="2df35-123">**Response Body** - Below is a sample log status.</span></span>
  
```
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
