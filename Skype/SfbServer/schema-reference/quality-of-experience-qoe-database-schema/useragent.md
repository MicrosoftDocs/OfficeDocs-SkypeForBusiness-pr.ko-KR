---
title: UserAgent 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196514"
---
# <a name="useragent-table"></a><span data-ttu-id="57fa5-104">UserAgent 테이블</span><span class="sxs-lookup"><span data-stu-id="57fa5-104">UserAgent table</span></span>
 
<span data-ttu-id="57fa5-105">UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="57fa5-106">테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="57fa5-107">**열**</span><span class="sxs-lookup"><span data-stu-id="57fa5-107">**Column**</span></span>|<span data-ttu-id="57fa5-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="57fa5-108">**Data Type**</span></span>|<span data-ttu-id="57fa5-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="57fa5-109">**Key/Index**</span></span>|<span data-ttu-id="57fa5-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="57fa5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57fa5-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="57fa5-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="57fa5-112">int</span><span class="sxs-lookup"><span data-stu-id="57fa5-112">int</span></span>  <br/> |<span data-ttu-id="57fa5-113">주요한</span><span class="sxs-lookup"><span data-stu-id="57fa5-113">Primary</span></span>  <br/> |<span data-ttu-id="57fa5-114">이 사용자 에이전트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="57fa5-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="57fa5-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="57fa5-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57fa5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="57fa5-117">독특한</span><span class="sxs-lookup"><span data-stu-id="57fa5-117">Unique</span></span>  <br/> |<span data-ttu-id="57fa5-118">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="57fa5-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="57fa5-119">**UAType**</span></span> <br/> |<span data-ttu-id="57fa5-120">smallint</span><span class="sxs-lookup"><span data-stu-id="57fa5-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="57fa5-121">1은 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="57fa5-122">2는 A/V 회의 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="57fa5-123">4 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="57fa5-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="57fa5-124">8은 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="57fa5-125">16 개는 Live Meeting Console입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="57fa5-126">32는 DVT (배포 유효성 검사 도구)입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="57fa5-127">Macintosh 컴퓨터의 비즈니스용 Skype 서버는 64입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="57fa5-128">128는 비즈니스용 Skype 서버 수행자입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="57fa5-129">256는 회의 알림 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="57fa5-130">512는 회의 자동 전화 교환입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="57fa5-131">1024는 응답 그룹 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="57fa5-132">2048는 음성 제어를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="57fa5-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

