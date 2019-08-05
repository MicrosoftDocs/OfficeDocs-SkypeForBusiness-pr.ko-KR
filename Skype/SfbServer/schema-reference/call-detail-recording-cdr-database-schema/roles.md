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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: '역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.'
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196694"
---
# <a name="roles-table"></a><span data-ttu-id="ffb82-103">Roles 테이블</span><span class="sxs-lookup"><span data-stu-id="ffb82-103">Roles table</span></span>
 
<span data-ttu-id="ffb82-104">역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb82-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="ffb82-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ffb82-105">**Column**</span></span>|<span data-ttu-id="ffb82-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="ffb82-106">**Data Type**</span></span>|<span data-ttu-id="ffb82-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="ffb82-107">**Key/Index**</span></span>|<span data-ttu-id="ffb82-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="ffb82-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ffb82-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="ffb82-109">**RoleId**</span></span> <br/> |<span data-ttu-id="ffb82-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ffb82-110">tinyint</span></span>  <br/> |<span data-ttu-id="ffb82-111">주요한</span><span class="sxs-lookup"><span data-stu-id="ffb82-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ffb82-112">**역할인**</span><span class="sxs-lookup"><span data-stu-id="ffb82-112">**Role**</span></span> <br/> |<span data-ttu-id="ffb82-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ffb82-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ffb82-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="ffb82-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ffb82-115">0-알 수 없음</span><span class="sxs-lookup"><span data-stu-id="ffb82-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ffb82-116">1-발표자</span><span class="sxs-lookup"><span data-stu-id="ffb82-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="ffb82-117">2-참석자</span><span class="sxs-lookup"><span data-stu-id="ffb82-117">2 - Attendee</span></span> <br/> |
   

