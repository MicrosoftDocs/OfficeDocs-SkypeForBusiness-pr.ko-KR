---
title: 사용자 가져오기
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '요약: 사용자 서비스의 일부인 사용자 Get 사용자 작업에 대해 자세히 알아보습니다. 사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832418"
---
# <a name="get-user"></a><span data-ttu-id="394a9-105">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="394a9-105">Get User</span></span>
 
<span data-ttu-id="394a9-106">**요약:** 사용자 서비스의 일부인 사용자 Get 사용자 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="394a9-107">사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="394a9-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="394a9-109">사용자 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="394a9-110">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="394a9-110">Get User</span></span>

<span data-ttu-id="394a9-111">사용자 레코드를 리포지토리에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="394a9-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="394a9-112">**Method**</span></span>|<span data-ttu-id="394a9-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="394a9-113">**Request URI**</span></span>|<span data-ttu-id="394a9-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="394a9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="394a9-115">GET</span><span class="sxs-lookup"><span data-stu-id="394a9-115">GET</span></span>  <br/> |<span data-ttu-id="394a9-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="394a9-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="394a9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="394a9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="394a9-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="394a9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="394a9-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="394a9-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="394a9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="394a9-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="394a9-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="394a9-123">지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="394a9-124">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="394a9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="394a9-125">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="394a9-126">*userId*  - 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="394a9-127">*loginName*  - 일반 사용자의 외부 사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="394a9-128">Windows 인증을 사용하여 사용자를 인증하는 경우 사용자의 FQDN일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="394a9-129">*defaultItemId*  - 이 사용자의 기본 항목 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="394a9-130">기본 항목은 사용자에게 연결된 최상위 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="394a9-131">이 사용자가 소유한 다른 모든 항목은 기본 항목에서 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="394a9-132">기본 항목의 세부 정보를 검색하기 위해 항목 Get 작업에  `defaultItemId` 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="394a9-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

