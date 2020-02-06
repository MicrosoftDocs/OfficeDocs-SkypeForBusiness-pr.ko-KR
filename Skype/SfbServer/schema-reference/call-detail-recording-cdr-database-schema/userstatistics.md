---
title: UserStatistics 테이블
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 테이블은 지원 테이블입니다. 표의 각 레코드에는 시스템의 개별 사용자 사용에 대 한 정보가 저장 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814796"
---
# <a name="userstatistics-table"></a><span data-ttu-id="f74dd-105">UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="f74dd-105">UserStatistics table</span></span>
 
<span data-ttu-id="f74dd-106">UserStatistics 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="f74dd-107">표의 각 레코드에는 시스템의 개별 사용자 사용에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="f74dd-108">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f74dd-109">**열**</span><span class="sxs-lookup"><span data-stu-id="f74dd-109">**Column**</span></span>|<span data-ttu-id="f74dd-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="f74dd-110">**Data Type**</span></span>|<span data-ttu-id="f74dd-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="f74dd-111">**Key/Index**</span></span>|<span data-ttu-id="f74dd-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="f74dd-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f74dd-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="f74dd-113">**UserId**</span></span> <br/> |<span data-ttu-id="f74dd-114">int</span><span class="sxs-lookup"><span data-stu-id="f74dd-114">int</span></span>  <br/> |<span data-ttu-id="f74dd-115">주요한</span><span class="sxs-lookup"><span data-stu-id="f74dd-115">Primary</span></span>  <br/> |<span data-ttu-id="f74dd-116">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="f74dd-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="f74dd-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="f74dd-118">dmtf</span><span class="sxs-lookup"><span data-stu-id="f74dd-118">datetime</span></span>  <br/> ||<span data-ttu-id="f74dd-119">사용자가 마지막으로 로그인 한 시간</span><span class="sxs-lookup"><span data-stu-id="f74dd-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="f74dd-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="f74dd-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="f74dd-121">dmtf</span><span class="sxs-lookup"><span data-stu-id="f74dd-121">datetime</span></span>  <br/> ||<span data-ttu-id="f74dd-122">사용자가 회의를 마지막으로 구성한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="f74dd-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="f74dd-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="f74dd-124">dmtf</span><span class="sxs-lookup"><span data-stu-id="f74dd-124">datetime</span></span>  <br/> ||<span data-ttu-id="f74dd-125">마지막으로 사용자에 게 전화 실패가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="f74dd-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="f74dd-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="f74dd-127">dmtf</span><span class="sxs-lookup"><span data-stu-id="f74dd-127">datetime</span></span>  <br/> ||<span data-ttu-id="f74dd-128">마지막으로 사용자에 게 컨퍼런스 이끌이로 인해 전화 실패가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f74dd-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

