---
title: 항목 가져오기
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '요약: 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832538"
---
# <a name="get-items"></a><span data-ttu-id="9a042-105">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="9a042-105">Get Items</span></span>
 
<span data-ttu-id="9a042-106">**요약:** 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="9a042-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9a042-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9a042-109">항목 항목 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="9a042-110">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="9a042-110">Get Items</span></span>

<span data-ttu-id="9a042-111">Get Items는 리포지토리의 모든 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="9a042-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="9a042-112">**Method**</span></span>|<span data-ttu-id="9a042-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="9a042-113">**Request URI**</span></span>|<span data-ttu-id="9a042-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="9a042-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a042-115">GET</span><span class="sxs-lookup"><span data-stu-id="9a042-115">GET</span></span>  <br/> |<span data-ttu-id="9a042-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="9a042-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="9a042-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9a042-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9a042-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="9a042-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9a042-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9a042-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="9a042-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9a042-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9a042-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9a042-123">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="9a042-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9a042-124">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a042-125">Item 개체의 배열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-125">An array of Item objects is returned.</span></span> <span data-ttu-id="9a042-126">Item 개체에 대한 자세한 내용은 항목 보기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9a042-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
