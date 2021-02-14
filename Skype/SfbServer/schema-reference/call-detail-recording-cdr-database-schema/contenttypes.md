---
title: 비즈니스용 Skype 서버의 ContentTypes 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 테이블은 피어-투-피어 세션 및 회의 세션에 사용되는 콘텐츠 유형 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 콘텐츠 유형을 나타냅니다.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816088"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4bd0c-104">비즈니스용 Skype 서버의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="4bd0c-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4bd0c-p102">ContentTypes 테이블은 피어-투-피어 세션 및 회의 세션에 사용되는 콘텐츠 유형 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 콘텐츠 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-p102">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="4bd0c-107">**열**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-107">**Column**</span></span>|<span data-ttu-id="4bd0c-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-108">**Data Type**</span></span>|<span data-ttu-id="4bd0c-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-109">**Key/Index**</span></span>|<span data-ttu-id="4bd0c-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4bd0c-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="4bd0c-112">int</span><span class="sxs-lookup"><span data-stu-id="4bd0c-112">int</span></span>  <br/> |<span data-ttu-id="4bd0c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4bd0c-113">Primary</span></span>  <br/> |<span data-ttu-id="4bd0c-114">콘텐츠 유형을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="4bd0c-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="4bd0c-115">**ContentType**</span></span> <br/> |<span data-ttu-id="4bd0c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4bd0c-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="4bd0c-117">콘텐츠 유형 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd0c-117">Content type name.</span></span>  <br/> |
   

