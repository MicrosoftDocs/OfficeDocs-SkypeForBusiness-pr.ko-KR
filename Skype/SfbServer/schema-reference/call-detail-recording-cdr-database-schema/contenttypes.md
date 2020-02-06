---
title: 비즈니스용 Skype 서버 2015의 ContentTypes 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 테이블은 피어 투 피어 세션과 회의 세션에 사용 되는 콘텐츠 형식의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 가지 콘텐츠 형식을 나타냅니다.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815306"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="52f1f-104">비즈니스용 Skype 서버 2015의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="52f1f-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52f1f-105">ContentTypes 테이블은 피어 투 피어 세션과 회의 세션에 사용 되는 콘텐츠 형식의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="52f1f-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="52f1f-106">테이블의 각 레코드는 한 가지 콘텐츠 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52f1f-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="52f1f-107">**열**</span><span class="sxs-lookup"><span data-stu-id="52f1f-107">**Column**</span></span>|<span data-ttu-id="52f1f-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="52f1f-108">**Data Type**</span></span>|<span data-ttu-id="52f1f-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="52f1f-109">**Key/Index**</span></span>|<span data-ttu-id="52f1f-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="52f1f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52f1f-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="52f1f-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="52f1f-112">int</span><span class="sxs-lookup"><span data-stu-id="52f1f-112">int</span></span>  <br/> |<span data-ttu-id="52f1f-113">주요한</span><span class="sxs-lookup"><span data-stu-id="52f1f-113">Primary</span></span>  <br/> |<span data-ttu-id="52f1f-114">콘텐츠 형식을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="52f1f-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="52f1f-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="52f1f-115">**ContentType**</span></span> <br/> |<span data-ttu-id="52f1f-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52f1f-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="52f1f-117">콘텐츠 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52f1f-117">Content type name.</span></span>  <br/> |
   

