---
title: 사용자 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '요약: 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다. 사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186888"
---
# <a name="get-users"></a><span data-ttu-id="d277c-105">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="d277c-105">Get Users</span></span>
 
<span data-ttu-id="d277c-106">**요약:** 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="d277c-107">사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d277c-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d277c-109">사용자 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="d277c-110">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="d277c-110">Get Users</span></span>

<span data-ttu-id="d277c-111">사용자 가져오기 저장소의 사용자 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="d277c-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="d277c-112">**Method**</span></span>|<span data-ttu-id="d277c-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="d277c-113">**Request URI**</span></span>|<span data-ttu-id="d277c-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="d277c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d277c-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="d277c-115">GET</span></span>  <br/> |<span data-ttu-id="d277c-116">https://\<포털\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="d277c-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="d277c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d277c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d277c-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="d277c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d277c-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d277c-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="d277c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d277c-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d277c-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d277c-123">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d277c-124">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d277c-125">사용자 개체의 배열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d277c-125">An array of User objects is returned.</span></span> <span data-ttu-id="d277c-126">사용자 개체에 대 한 자세한 내용은 사용자 가져오기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d277c-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


