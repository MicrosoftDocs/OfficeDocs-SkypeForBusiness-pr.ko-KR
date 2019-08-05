---
title: 항목 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '요약: 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186930"
---
# <a name="get-items"></a><span data-ttu-id="53e85-105">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="53e85-105">Get Items</span></span>
 
<span data-ttu-id="53e85-106">**요약:** 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="53e85-107">항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="53e85-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="53e85-109">항목 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="53e85-110">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="53e85-110">Get Items</span></span>

<span data-ttu-id="53e85-111">항목 가져오기 저장소의 모든 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="53e85-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="53e85-112">**Method**</span></span>|<span data-ttu-id="53e85-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="53e85-113">**Request URI**</span></span>|<span data-ttu-id="53e85-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="53e85-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53e85-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="53e85-115">GET</span></span>  <br/> |<span data-ttu-id="53e85-116">https://\<포털\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="53e85-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="53e85-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="53e85-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="53e85-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="53e85-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="53e85-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="53e85-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="53e85-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="53e85-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="53e85-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="53e85-123">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="53e85-124">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53e85-125">항목 개체의 배열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53e85-125">An array of Item objects is returned.</span></span> <span data-ttu-id="53e85-126">Item 개체에 대 한 자세한 내용은 항목 가져오기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53e85-126">For details about Item object, see Get Item.</span></span> 
  
```
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
