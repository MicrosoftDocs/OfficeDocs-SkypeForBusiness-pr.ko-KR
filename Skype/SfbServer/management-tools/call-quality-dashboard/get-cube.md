---
title: 큐브 가져오기
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 큐브 가져오기 작업에 대해 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 7ae24309ea49d8f7d8d2684c141adb44c5bff2b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816837"
---
# <a name="get-cube"></a><span data-ttu-id="38dd7-104">큐브 가져오기</span><span class="sxs-lookup"><span data-stu-id="38dd7-104">Get Cube</span></span>
 
<span data-ttu-id="38dd7-105">**요약:** 통화 품질 대시보드의 데이터 API의 일부인 큐브 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="38dd7-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="38dd7-107">큐브 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="38dd7-108">큐브 가져오기</span><span class="sxs-lookup"><span data-stu-id="38dd7-108">Get Cube</span></span>

<span data-ttu-id="38dd7-109">큐브 가져오기 작업은 사용 가능한 차원과 측정값의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="38dd7-110">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="38dd7-110">**Method**</span></span>|<span data-ttu-id="38dd7-111">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="38dd7-111">**Request URI**</span></span>|<span data-ttu-id="38dd7-112">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="38dd7-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38dd7-113">가져오기</span><span class="sxs-lookup"><span data-stu-id="38dd7-113">GET</span></span>  <br/> |<span data-ttu-id="38dd7-114">https://\<portal\>/Qoedataservice/cubestructure</span><span class="sxs-lookup"><span data-stu-id="38dd7-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="38dd7-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="38dd7-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="38dd7-116">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="38dd7-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="38dd7-117">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="38dd7-118">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="38dd7-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="38dd7-119">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="38dd7-120">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="38dd7-121">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="38dd7-122">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38dd7-123">이 샘플은 각 큐브 요소 그룹의 처음 두 요소만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="38dd7-124">*Kpi* -예약 됨.</span><span class="sxs-lookup"><span data-stu-id="38dd7-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="38dd7-125">요청 페이로드의 Kpi 섹션을 사용 하면 쿼리 실행 작업에서 큐브에 정의 된 Kpi에 대 한 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="38dd7-126">체감 품질 큐브에 Kpi가 아직 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="38dd7-127">*차원* -쿼리 실행 작업에 대 한 요청 페이로드의 필터 및 차원 섹션에서 사용할 수 있는 차원의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="38dd7-128">필터 식에서 차원을 사용 하려면 차원 구성원 가져오기 작업을 사용 하 여 가져올 수 있는 차원 구성원을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="38dd7-129">*단위* -쿼리 실행 작업에 대 한 요청 페이로드의 측정 섹션에서 사용할 수 있는 측정값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="38dd7-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

