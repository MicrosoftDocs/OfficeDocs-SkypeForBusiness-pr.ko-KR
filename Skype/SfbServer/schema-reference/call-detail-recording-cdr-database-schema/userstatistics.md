---
title: UserStatistics 테이블
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 개별 사용자의 시스템 사용에 대한 정보가 저장됩니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813108"
---
# <a name="userstatistics-table"></a><span data-ttu-id="72f88-105">UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="72f88-105">UserStatistics table</span></span>
 
<span data-ttu-id="72f88-106">UserStatistics 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="72f88-107">테이블의 각 레코드에는 개별 사용자의 시스템 사용에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="72f88-108">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="72f88-109">**열**</span><span class="sxs-lookup"><span data-stu-id="72f88-109">**Column**</span></span>|<span data-ttu-id="72f88-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="72f88-110">**Data Type**</span></span>|<span data-ttu-id="72f88-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="72f88-111">**Key/Index**</span></span>|<span data-ttu-id="72f88-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="72f88-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72f88-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="72f88-113">**UserId**</span></span> <br/> |<span data-ttu-id="72f88-114">int</span><span class="sxs-lookup"><span data-stu-id="72f88-114">int</span></span>  <br/> |<span data-ttu-id="72f88-115">Primary</span><span class="sxs-lookup"><span data-stu-id="72f88-115">Primary</span></span>  <br/> |<span data-ttu-id="72f88-116">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="72f88-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="72f88-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="72f88-118">datetime</span><span class="sxs-lookup"><span data-stu-id="72f88-118">datetime</span></span>  <br/> ||<span data-ttu-id="72f88-119">사용자가 마지막으로 로그인한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="72f88-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="72f88-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="72f88-121">datetime</span><span class="sxs-lookup"><span data-stu-id="72f88-121">datetime</span></span>  <br/> ||<span data-ttu-id="72f88-122">사용자가 마지막으로 회의를 구성한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="72f88-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="72f88-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="72f88-124">datetime</span><span class="sxs-lookup"><span data-stu-id="72f88-124">datetime</span></span>  <br/> ||<span data-ttu-id="72f88-125">사용자가 마지막으로 통화에 실패한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="72f88-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="72f88-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="72f88-127">datetime</span><span class="sxs-lookup"><span data-stu-id="72f88-127">datetime</span></span>  <br/> ||<span data-ttu-id="72f88-128">사용자가 마지막으로 전화 회의 이끌이로 통화에 실패한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

