---
title: UriTypes 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링 하는 다양 한 URI (Uniform resource identifier) 형식이 포함 되어 있습니다.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814846"
---
# <a name="uritypes-table"></a><span data-ttu-id="57b97-103">UriTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="57b97-103">UriTypes table</span></span>
 
<span data-ttu-id="57b97-104">UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링 하는 다양 한 URI (Uniform resource identifier) 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="57b97-105">CDR DB가 만들어지면 PhoneUri 및 UserUri를 나타내는 두 개의 레코드가 만들어지고 그 후에 생성 된 레코드가 UriTypeId에 동적으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="57b97-106">**열**</span><span class="sxs-lookup"><span data-stu-id="57b97-106">**Column**</span></span>|<span data-ttu-id="57b97-107">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="57b97-107">**Data Type**</span></span>|<span data-ttu-id="57b97-108">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="57b97-108">**Key/Index**</span></span>|<span data-ttu-id="57b97-109">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="57b97-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57b97-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="57b97-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="57b97-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="57b97-111">tinyint</span></span>  <br/> |<span data-ttu-id="57b97-112">주요한</span><span class="sxs-lookup"><span data-stu-id="57b97-112">Primary</span></span>  <br/> |<span data-ttu-id="57b97-113">URI 형식에 할당 된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="57b97-114">사용할 수 있는 값-0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="57b97-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="57b97-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="57b97-115">**UriType**</span></span> <br/> |<span data-ttu-id="57b97-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57b97-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="57b97-117">다양 한 URI 형식에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="57b97-118">미리 지정 된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="57b97-119">1-전화 Uri</span><span class="sxs-lookup"><span data-stu-id="57b97-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="57b97-120">0-사용자 Uri</span><span class="sxs-lookup"><span data-stu-id="57b97-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="57b97-121">다른 종류의 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57b97-121">Other possible types include:</span></span> <br/><span data-ttu-id="57b97-122">회의: applicationsharing</span><span class="sxs-lookup"><span data-stu-id="57b97-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="57b97-123">회의: 오디오-영상</span><span class="sxs-lookup"><span data-stu-id="57b97-123">conf:audio-video</span></span><br/> <span data-ttu-id="57b97-124">회의: 채팅</span><span class="sxs-lookup"><span data-stu-id="57b97-124">conf:chat</span></span><br/>    <span data-ttu-id="57b97-125">회의: 포커스</span><span class="sxs-lookup"><span data-stu-id="57b97-125">conf:focus</span></span><br/>   <span data-ttu-id="57b97-126">mras</span><span class="sxs-lookup"><span data-stu-id="57b97-126">mras</span></span><br/>
