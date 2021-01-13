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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '요약: 사용자 서비스의 일부인 사용자 Get Users 작업에 대해 자세히 알아보습니다. 사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832428"
---
# <a name="get-users"></a><span data-ttu-id="5d231-105">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="5d231-105">Get Users</span></span>
 
<span data-ttu-id="5d231-106">**요약:** 사용자 서비스의 일부인 사용자 Get Users 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="5d231-107">사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5d231-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5d231-109">사용자 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="5d231-110">사용자 가져오기</span><span class="sxs-lookup"><span data-stu-id="5d231-110">Get Users</span></span>

<span data-ttu-id="5d231-111">사용자가 리포지토리에 있는 사용자 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="5d231-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="5d231-112">**Method**</span></span>|<span data-ttu-id="5d231-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="5d231-113">**Request URI**</span></span>|<span data-ttu-id="5d231-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="5d231-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d231-115">GET</span><span class="sxs-lookup"><span data-stu-id="5d231-115">GET</span></span>  <br/> |<span data-ttu-id="5d231-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="5d231-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="5d231-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5d231-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5d231-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="5d231-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5d231-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5d231-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="5d231-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5d231-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5d231-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="5d231-123">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="5d231-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5d231-124">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d231-125">User 개체의 배열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-125">An array of User objects is returned.</span></span> <span data-ttu-id="5d231-126">User 개체에 대한 자세한 내용은 사용자 보기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5d231-126">For details about the User object, see Get User.</span></span> 
  
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


