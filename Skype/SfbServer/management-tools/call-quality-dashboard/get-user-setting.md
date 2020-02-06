---
title: 사용자 설정 가져오기
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '요약: 사용자 설정 서비스의 일부인 사용자 가져오기 설정 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 4ab9d4d718a2ff411db72f38b59a758523935504
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816757"
---
# <a name="get-user-setting"></a><span data-ttu-id="01032-105">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="01032-105">Get User Setting</span></span>
 
<span data-ttu-id="01032-106">**요약:** 사용자 설정 서비스의 일부인 사용자 가져오기 설정 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="01032-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="01032-107">사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="01032-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="01032-109">사용자 가져오기 설정 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 설정 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="01032-110">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="01032-110">Get User Setting</span></span>

<span data-ttu-id="01032-111">사용자 설정 가져오기 단일 사용자 설정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01032-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="01032-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="01032-112">**Method**</span></span>|<span data-ttu-id="01032-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="01032-113">**Request URI**</span></span>|<span data-ttu-id="01032-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="01032-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="01032-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="01032-115">GET</span></span>  <br/> |<span data-ttu-id="01032-116">https://\<포털\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="01032-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="01032-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="01032-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="01032-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="01032-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="01032-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01032-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="01032-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="01032-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="01032-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01032-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="01032-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01032-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="01032-123">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01032-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="01032-124">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="01032-125">*userId* -사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="01032-126">setting의 *key* 키입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="01032-127">*value* -설정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01032-127">*value*  - Value of the setting.</span></span>
  

