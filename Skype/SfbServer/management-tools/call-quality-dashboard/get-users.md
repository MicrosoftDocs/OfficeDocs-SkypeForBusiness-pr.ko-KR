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
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992615"
---
# <a name="get-users"></a><span data-ttu-id="eeb78-105">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="eeb78-105">Get Users</span></span>
 
<span data-ttu-id="eeb78-106">**요약:** 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="eeb78-107">사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="eeb78-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="eeb78-109">사용자 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="eeb78-110">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="eeb78-110">Get Users</span></span>

<span data-ttu-id="eeb78-111">사용자 가져오기 저장소의 사용자 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="eeb78-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="eeb78-112">**Method**</span></span>|<span data-ttu-id="eeb78-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="eeb78-113">**Request URI**</span></span>|<span data-ttu-id="eeb78-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="eeb78-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eeb78-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="eeb78-115">GET</span></span>  <br/> |<span data-ttu-id="eeb78-116">https://\<포털\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="eeb78-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="eeb78-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="eeb78-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="eeb78-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="eeb78-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="eeb78-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eeb78-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="eeb78-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="eeb78-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="eeb78-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="eeb78-123">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eeb78-124">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eeb78-125">사용자 개체의 배열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb78-125">An array of User objects is returned.</span></span> <span data-ttu-id="eeb78-126">사용자 개체에 대 한 자세한 내용은 사용자 가져오기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eeb78-126">For details about the User object, see Get User.</span></span> 
  
```json
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


