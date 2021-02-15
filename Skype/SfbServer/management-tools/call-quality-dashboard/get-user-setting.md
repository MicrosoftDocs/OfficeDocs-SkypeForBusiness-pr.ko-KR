---
title: 사용자 설정 가져오기
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '요약: 사용자 설정 서비스의 일부인 사용자 설정 사용 작업에 대해 자세히 알아보습니다. 사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832488"
---
# <a name="get-user-setting"></a><span data-ttu-id="bec42-105">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="bec42-105">Get User Setting</span></span>
 
<span data-ttu-id="bec42-106">**요약:** 사용자 설정 서비스의 일부인 사용자 설정 사용 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="bec42-107">사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bec42-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bec42-109">사용자 설정 저장 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 설정 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="bec42-110">사용자 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="bec42-110">Get User Setting</span></span>

<span data-ttu-id="bec42-111">사용자 설정에서 단일 사용자 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="bec42-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="bec42-112">**Method**</span></span>|<span data-ttu-id="bec42-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="bec42-113">**Request URI**</span></span>|<span data-ttu-id="bec42-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="bec42-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bec42-115">GET</span><span class="sxs-lookup"><span data-stu-id="bec42-115">GET</span></span>  <br/> |<span data-ttu-id="bec42-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="bec42-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="bec42-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bec42-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bec42-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="bec42-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bec42-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bec42-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="bec42-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bec42-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bec42-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bec42-123">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="bec42-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bec42-124">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="bec42-125">*userId*  - 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="bec42-126">*key*  - 설정의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="bec42-127">*value*  - 설정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bec42-127">*value*  - Value of the setting.</span></span>
  

