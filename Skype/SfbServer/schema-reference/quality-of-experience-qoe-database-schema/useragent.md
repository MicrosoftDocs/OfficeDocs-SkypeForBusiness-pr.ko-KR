---
title: UserAgent 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 테이블은 데이터베이스에 기록된 세션에 참여한 다양한 사용자 에이전트 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 사용자 에이전트를 나타 내는 경우
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799938"
---
# <a name="useragent-table"></a><span data-ttu-id="52308-104">UserAgent 테이블</span><span class="sxs-lookup"><span data-stu-id="52308-104">UserAgent table</span></span>
 
<span data-ttu-id="52308-105">UserAgent 테이블은 데이터베이스에 기록된 세션에 참여한 다양한 사용자 에이전트 목록을 저장하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="52308-106">테이블의 각 레코드는 하나의 사용자 에이전트를 나타 내는 경우</span><span class="sxs-lookup"><span data-stu-id="52308-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="52308-107">**열**</span><span class="sxs-lookup"><span data-stu-id="52308-107">**Column**</span></span>|<span data-ttu-id="52308-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="52308-108">**Data Type**</span></span>|<span data-ttu-id="52308-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="52308-109">**Key/Index**</span></span>|<span data-ttu-id="52308-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="52308-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52308-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="52308-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="52308-112">int</span><span class="sxs-lookup"><span data-stu-id="52308-112">int</span></span>  <br/> |<span data-ttu-id="52308-113">Primary</span><span class="sxs-lookup"><span data-stu-id="52308-113">Primary</span></span>  <br/> |<span data-ttu-id="52308-114">이 사용자 에이전트를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="52308-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="52308-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="52308-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="52308-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="52308-117">고유</span><span class="sxs-lookup"><span data-stu-id="52308-117">Unique</span></span>  <br/> |<span data-ttu-id="52308-118">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="52308-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="52308-119">**UAType**</span></span> <br/> |<span data-ttu-id="52308-120">smallint</span><span class="sxs-lookup"><span data-stu-id="52308-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="52308-121">1은 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="52308-122">2는 A/V 회의 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="52308-123">4는 비즈니스용 Skype입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="52308-124">8은 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="52308-125">16은 Live Meeting Console입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="52308-126">32는 DVT(배포 유효성 검사 도구)입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="52308-127">64는 Macintosh 컴퓨터의 비즈니스용 Skype 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="52308-128">128은 비즈니스용 Skype 서버 Attendant입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="52308-129">256은 회의 공지 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="52308-130">512는 회의 자동 전화 교환.</span><span class="sxs-lookup"><span data-stu-id="52308-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="52308-131">1024는 응답 그룹 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="52308-132">2048은 외부 음성 제어입니다.</span><span class="sxs-lookup"><span data-stu-id="52308-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

