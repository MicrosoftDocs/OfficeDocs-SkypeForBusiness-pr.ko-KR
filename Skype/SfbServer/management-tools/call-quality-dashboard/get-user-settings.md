---
title: 사용자 설정 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '요약: 사용자 설정 서비스의 일부인 사용자 설정 가져오기 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186894"
---
# <a name="get-user-settings"></a><span data-ttu-id="dd3a1-105">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="dd3a1-105">Get User Settings</span></span>
 
<span data-ttu-id="dd3a1-106">**요약:** 사용자 설정 서비스의 일부인 사용자 설정 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="dd3a1-107">사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dd3a1-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dd3a1-109">사용자 설정 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 설정 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="dd3a1-110">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="dd3a1-110">Get User Settings</span></span>

<span data-ttu-id="dd3a1-111">사용자 설정 가져오기 지정 된 사용자에 대 한 설정 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="dd3a1-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="dd3a1-112">**Method**</span></span>|<span data-ttu-id="dd3a1-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="dd3a1-113">**Request URI**</span></span>|<span data-ttu-id="dd3a1-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="dd3a1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd3a1-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="dd3a1-115">GET</span></span>  <br/> |<span data-ttu-id="dd3a1-116">https://\<포털\>/QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="dd3a1-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="dd3a1-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="dd3a1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="dd3a1-118">**URI 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="dd3a1-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="dd3a1-119">*유효* -선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-119">*effective*  - Optional.</span></span> <span data-ttu-id="dd3a1-120">이 매개 변수는 특별 한 사용자 ID default를 사용 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="dd3a1-121">다른 경우에는이를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="dd3a1-122">`True`유효 사용자 설정을 반환 하 `false` 고 사용자 설정만 반환 합니다 (기본값).</span><span class="sxs-lookup"><span data-stu-id="dd3a1-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="dd3a1-123">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="dd3a1-124">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="dd3a1-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="dd3a1-125">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="dd3a1-126">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="dd3a1-127">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="dd3a1-128">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
