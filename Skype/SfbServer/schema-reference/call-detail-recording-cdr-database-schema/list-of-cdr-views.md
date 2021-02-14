---
title: CDR 보기 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 보기를 통해 CDR 데이터베이스에서 데이터를 반환하는 데 사용되는 가장 일반적인 시나리오에 대한 정보에 쉽게 액세스할 수 있습니다. 실제 CDR 데이터베이스 테이블을 사용하는 대신 보기를 사용하여 사용자 지정 보고서를 작성하는 것이 좋습니다. 이는 데이터베이스 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813158"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="d9343-104">CDR 보기 목록</span><span class="sxs-lookup"><span data-stu-id="d9343-104">List of CDR views</span></span>
 
<span data-ttu-id="d9343-105">보기를 통해 CDR 데이터베이스에서 데이터를 반환하는 데 사용되는 가장 일반적인 시나리오에 대한 정보에 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="d9343-106">실제 CDR 데이터베이스 테이블을 사용하는 대신 보기를 사용하여 사용자 지정 보고서를 작성하는 것이 좋습니다. 이는 데이터베이스 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="d9343-107">**뷰 이름/View Name**</span><span class="sxs-lookup"><span data-stu-id="d9343-107">**View Name**</span></span>|<span data-ttu-id="d9343-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="d9343-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d9343-109">ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="d9343-110">통신 세션에서 사용되는 클라이언트 소프트웨어/장치에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="d9343-111">ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="d9343-112">전화 회의에서 사용자가 보낸 메시지 수에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="d9343-113">회의 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="d9343-114">시작 시간, 종료 시간, 전화 회의 이끌이 등의 전화 회의 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="d9343-115">ConferenceSessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="d9343-116">시작/종료 시간, 사용자 ID, 응답 코드, 진단 ID를 포함하여 모든 전화 회의 세션에 대한 세션 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="d9343-117">ConferenceUris 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="d9343-118">전화 회의에서 사용되는 전화 회의 URI에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="d9343-119">ErrorReport 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="d9343-120">세션 중 발생한 오류에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="d9343-121">FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="d9343-122">파일 이름 및 전송 수락/거절/취소 여부를 포함하여 파일 전송 세션에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="d9343-123">FocusJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="d9343-124">전화 회의 참가 및 나가기 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="d9343-125">McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="d9343-126">전화 회의 참가 및 나가기 활동에 대한 결합된 정보를 반환합니다(각 전화 회의 참가는 해당하는 전화 회의 나가기와 쌍으로 지정됨).</span><span class="sxs-lookup"><span data-stu-id="d9343-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="d9343-127">Mcus 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="d9343-128">전화 회의 서버에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="d9343-129">미디어 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="d9343-130">피어 투 피어 통신 세션에서 사용되는 미디어 유형에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="d9343-131">ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="d9343-132">완료된 세션에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="d9343-133">등록 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="d9343-134">비즈니스용 Skype 서버 2015의 등록에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="d9343-135">SessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="d9343-136">VoIP 간 전화 통화, 두 사용자 간의 IM 세션 또는 기타 피어 투 피어 통신 세션을 포함하여 피어 투 피어 세션에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="d9343-137">사용자 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="d9343-138">통신 세션에 참가한 사용자에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="d9343-139">VoIPDetails 보기</span><span class="sxs-lookup"><span data-stu-id="d9343-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="d9343-140">VoIP(Voice over IP) 사용자가 한 명 이상 포함된 피어 투 피어 세션에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9343-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

