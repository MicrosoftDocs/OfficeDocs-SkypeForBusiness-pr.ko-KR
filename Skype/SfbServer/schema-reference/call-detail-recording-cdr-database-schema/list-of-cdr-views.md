---
title: CDR 보기 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다. 실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 릴리스와 이전 버전과의 호환성을 유지 하는 것이 더 높기 때문입니다.
ms.openlocfilehash: e1a7926108c2e27ecc69c5717867b9c18f8b47ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196733"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="dae6c-104">CDR 보기 목록</span><span class="sxs-lookup"><span data-stu-id="dae6c-104">List of CDR views</span></span>
 
<span data-ttu-id="dae6c-105">뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="dae6c-106">실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 릴리스와 이전 버전과의 호환성을 유지 하는 것이 더 높기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="dae6c-107">**이름 보기**</span><span class="sxs-lookup"><span data-stu-id="dae6c-107">**View Name**</span></span>|<span data-ttu-id="dae6c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="dae6c-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dae6c-109">ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="dae6c-110">통신 세션에 사용 되는 클라이언트 소프트웨어/장치에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-111">ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="dae6c-112">회의 중 사용자가 보낸 메시지 수에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-113">회의 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="dae6c-114">시작 시간, 종료 시간, 컨퍼런스 이끌이 등 회의 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-115">ConferenceSessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="dae6c-116">시작 및 종료 시간, 사용자 Id, 응답 코드, 진단 Id를 포함 하 여 모든 회의 세션에 대 한 세션 세부 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-117">ConferenceUris 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="dae6c-118">회의에 사용 되는 회의 Uri에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="dae6c-119">ErrorReport 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="dae6c-120">세션 중에 발생 한 오류에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-121">FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="dae6c-122">파일 이름과 전송 수락, 거부 또는 취소를 포함 하 여 파일 전송 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-123">FocusJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="dae6c-124">컨퍼런스 참가 및 탈퇴 활동에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-125">McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="dae6c-126">컨퍼런스 참가 및 탈퇴 활동에 대 한 통합 된 정보를 반환 합니다 (각 회의 참가는 해당 회의 연결이 유지 됩니다.).</span><span class="sxs-lookup"><span data-stu-id="dae6c-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="dae6c-127">Mcus 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="dae6c-128">회의 서버에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-129">미디어 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="dae6c-130">피어 투 피어 통신 세션에 사용 되는 미디어 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-131">ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="dae6c-132">완료 된 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-133">등록 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="dae6c-134">비즈니스용 Skype Server 2015의 등록에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-135">SessionDetails 뷰</span><span class="sxs-lookup"><span data-stu-id="dae6c-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="dae6c-136">VoIP 전화 통화, 2 자리 IM 세션 또는 기타 피어 투 피어 통신 세션을 비롯 한 피어 투 피어 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-137">사용자 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="dae6c-138">통신 세션에 참가 한 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="dae6c-139">VoIPDetails 보기</span><span class="sxs-lookup"><span data-stu-id="dae6c-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="dae6c-140">하나 이상의 VoIP (음성 over IO) 사용자를 포함 하는 피어 투 피어 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dae6c-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

