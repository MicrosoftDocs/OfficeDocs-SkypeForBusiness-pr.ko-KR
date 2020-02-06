---
title: 사용자 가져오기
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '요약: 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다. 사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816737"
---
# <a name="get-user"></a><span data-ttu-id="356ae-105">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="356ae-105">Get User</span></span>
 
<span data-ttu-id="356ae-106">**요약:** 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="356ae-107">사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="356ae-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="356ae-109">사용자 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="356ae-110">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="356ae-110">Get User</span></span>

<span data-ttu-id="356ae-111">사용자가 리포지토리에서 사용자 레코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="356ae-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="356ae-112">**Method**</span></span>|<span data-ttu-id="356ae-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="356ae-113">**Request URI**</span></span>|<span data-ttu-id="356ae-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="356ae-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="356ae-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="356ae-115">GET</span></span>  <br/> |<span data-ttu-id="356ae-116">https://\<포털\>/QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="356ae-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="356ae-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="356ae-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="356ae-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="356ae-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="356ae-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="356ae-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="356ae-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="356ae-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="356ae-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="356ae-123">지정 된 사용자 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="356ae-124">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="356ae-125">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="356ae-126">*userId* -사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="356ae-127">*loginName* -일반 사용자에 대 한 외부 사용자 확인.</span><span class="sxs-lookup"><span data-stu-id="356ae-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="356ae-128">사용자 인증에 Windows 인증을 사용 하는 경우이는 사용자의 FQDN 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="356ae-129">*defaultItemId* -이 사용자에 대 한 기본 항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="356ae-130">기본 항목은 사용자에 게 연결 된 맨 위에 있는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="356ae-131">이 사용자가 소유한 다른 모든 항목은 기본 항목에서 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="356ae-132">항목 가져오기 `defaultItemId` 작업에 대 한 값을 제공 하 여 기본 항목의 세부 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="356ae-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

