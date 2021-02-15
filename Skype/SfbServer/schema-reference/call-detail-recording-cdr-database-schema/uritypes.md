---
title: UriTypes 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링되는 다른 URI(Uniform Resource Identifier) 유형이 포함되어 있습니다.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831688"
---
# <a name="uritypes-table"></a><span data-ttu-id="85eb5-103">UriTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="85eb5-103">UriTypes table</span></span>
 
<span data-ttu-id="85eb5-104">UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링되는 다른 URI(Uniform Resource Identifier) 유형이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="85eb5-105">CDR DB를 만들면 PhoneUri 및 UserUri를 나타내는 두 개의 레코드가 만들어지며 그 이후에 만들어진 레코드에는 동적으로 할당된 UriTypeId가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="85eb5-106">**열**</span><span class="sxs-lookup"><span data-stu-id="85eb5-106">**Column**</span></span>|<span data-ttu-id="85eb5-107">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="85eb5-107">**Data Type**</span></span>|<span data-ttu-id="85eb5-108">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="85eb5-108">**Key/Index**</span></span>|<span data-ttu-id="85eb5-109">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="85eb5-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85eb5-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="85eb5-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="85eb5-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="85eb5-111">tinyint</span></span>  <br/> |<span data-ttu-id="85eb5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="85eb5-112">Primary</span></span>  <br/> |<span data-ttu-id="85eb5-113">URI 유형에 지정된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="85eb5-114">가능한 값 - 0 ~255</span><span class="sxs-lookup"><span data-stu-id="85eb5-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="85eb5-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="85eb5-115">**UriType**</span></span> <br/> |<span data-ttu-id="85eb5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="85eb5-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="85eb5-117">다른 URI 유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="85eb5-118">다음 값은 미리 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="85eb5-119">1 - 전화 Uri</span><span class="sxs-lookup"><span data-stu-id="85eb5-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="85eb5-120">0 - 사용자 Uri</span><span class="sxs-lookup"><span data-stu-id="85eb5-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="85eb5-121">기타 가능한 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85eb5-121">Other possible types include:</span></span> <br/><span data-ttu-id="85eb5-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="85eb5-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="85eb5-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="85eb5-123">conf:audio-video</span></span><br/> <span data-ttu-id="85eb5-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="85eb5-124">conf:chat</span></span><br/>    <span data-ttu-id="85eb5-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="85eb5-125">conf:focus</span></span><br/>   <span data-ttu-id="85eb5-126">mras</span><span class="sxs-lookup"><span data-stu-id="85eb5-126">mras</span></span><br/>
