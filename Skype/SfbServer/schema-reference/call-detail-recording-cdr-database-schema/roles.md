---
title: Roles 테이블
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: '역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.'
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814936"
---
# <a name="roles-table"></a><span data-ttu-id="86b81-103">Roles 테이블</span><span class="sxs-lookup"><span data-stu-id="86b81-103">Roles table</span></span>
 
<span data-ttu-id="86b81-104">역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="86b81-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="86b81-105">**열**</span><span class="sxs-lookup"><span data-stu-id="86b81-105">**Column**</span></span>|<span data-ttu-id="86b81-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="86b81-106">**Data Type**</span></span>|<span data-ttu-id="86b81-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="86b81-107">**Key/Index**</span></span>|<span data-ttu-id="86b81-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="86b81-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="86b81-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="86b81-109">**RoleId**</span></span> <br/> |<span data-ttu-id="86b81-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="86b81-110">tinyint</span></span>  <br/> |<span data-ttu-id="86b81-111">주요한</span><span class="sxs-lookup"><span data-stu-id="86b81-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="86b81-112">**역할인**</span><span class="sxs-lookup"><span data-stu-id="86b81-112">**Role**</span></span> <br/> |<span data-ttu-id="86b81-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86b81-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="86b81-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="86b81-114">Allowed values:</span></span> <br/>  <span data-ttu-id="86b81-115">0-알 수 없음</span><span class="sxs-lookup"><span data-stu-id="86b81-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="86b81-116">1-발표자</span><span class="sxs-lookup"><span data-stu-id="86b81-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="86b81-117">2-참석자</span><span class="sxs-lookup"><span data-stu-id="86b81-117">2 - Attendee</span></span> <br/> |
   

