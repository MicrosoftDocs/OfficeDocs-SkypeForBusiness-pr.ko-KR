---
title: 비즈니스용 Skype 서버의 CallPriorities 테이블
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal'처럼 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813438"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="151d5-103">비즈니스용 Skype 서버의 CallPriorities 테이블</span><span class="sxs-lookup"><span data-stu-id="151d5-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="151d5-104">CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal'처럼 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="151d5-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="151d5-105">**열**</span><span class="sxs-lookup"><span data-stu-id="151d5-105">**Column**</span></span>|<span data-ttu-id="151d5-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="151d5-106">**Data Type**</span></span>|<span data-ttu-id="151d5-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="151d5-107">**Key/Index**</span></span>|<span data-ttu-id="151d5-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="151d5-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="151d5-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="151d5-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="151d5-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="151d5-110">tinyint</span></span>  <br/> |<span data-ttu-id="151d5-111">Primary</span><span class="sxs-lookup"><span data-stu-id="151d5-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="151d5-112">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="151d5-112">**Priority**</span></span> <br/> |<span data-ttu-id="151d5-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="151d5-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="151d5-114">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="151d5-114">Allowed values:</span></span> <br/>  <span data-ttu-id="151d5-115">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="151d5-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="151d5-116">1 - 긴급이 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="151d5-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="151d5-117">2 - 보통</span><span class="sxs-lookup"><span data-stu-id="151d5-117">2 - Normal</span></span> <br/>  <span data-ttu-id="151d5-118">3 - 긴급</span><span class="sxs-lookup"><span data-stu-id="151d5-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="151d5-119">4 - 응급</span><span class="sxs-lookup"><span data-stu-id="151d5-119">4 - Emergency</span></span> <br/> |
   

