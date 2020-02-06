---
title: 비즈니스용 Skype 서버 2015의 CallPriorities 순위 표
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 순위 테이블은 "비상 ', ' 긴급 ' 또는 ' normal ' 등의 가능한 통화 우선 순위 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815446"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ecf80-103">비즈니스용 Skype 서버 2015의 CallPriorities 순위 표</span><span class="sxs-lookup"><span data-stu-id="ecf80-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ecf80-104">CallPriorities 순위 테이블은 "비상 ', ' 긴급 ' 또는 ' normal ' 등의 가능한 통화 우선 순위 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="ecf80-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ecf80-105">**Column**</span></span>|<span data-ttu-id="ecf80-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="ecf80-106">**Data Type**</span></span>|<span data-ttu-id="ecf80-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="ecf80-107">**Key/Index**</span></span>|<span data-ttu-id="ecf80-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="ecf80-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecf80-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="ecf80-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="ecf80-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ecf80-110">tinyint</span></span>  <br/> |<span data-ttu-id="ecf80-111">주요한</span><span class="sxs-lookup"><span data-stu-id="ecf80-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ecf80-112">**중요도**</span><span class="sxs-lookup"><span data-stu-id="ecf80-112">**Priority**</span></span> <br/> |<span data-ttu-id="ecf80-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ecf80-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ecf80-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="ecf80-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ecf80-115">0-알 수 없음</span><span class="sxs-lookup"><span data-stu-id="ecf80-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ecf80-116">1-비 긴급</span><span class="sxs-lookup"><span data-stu-id="ecf80-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="ecf80-117">2-보통</span><span class="sxs-lookup"><span data-stu-id="ecf80-117">2 - Normal</span></span> <br/>  <span data-ttu-id="ecf80-118">3-긴급</span><span class="sxs-lookup"><span data-stu-id="ecf80-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="ecf80-119">4-긴급</span><span class="sxs-lookup"><span data-stu-id="ecf80-119">4 - Emergency</span></span> <br/> |
   

