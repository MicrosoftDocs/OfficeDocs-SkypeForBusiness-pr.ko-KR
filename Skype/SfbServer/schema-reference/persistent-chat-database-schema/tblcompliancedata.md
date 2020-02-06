---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814666"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="80878-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="80878-103">tblComplianceData</span></span>
 
<span data-ttu-id="80878-104">tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80878-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="80878-105">**열**</span><span class="sxs-lookup"><span data-stu-id="80878-105">**Columns**</span></span>

|<span data-ttu-id="80878-106">**열**</span><span class="sxs-lookup"><span data-stu-id="80878-106">**Column**</span></span>|<span data-ttu-id="80878-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="80878-107">**Type**</span></span>|<span data-ttu-id="80878-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="80878-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80878-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="80878-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="80878-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="80878-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="80878-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="80878-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="80878-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="80878-112">entryDate</span></span>  <br/> |<span data-ttu-id="80878-113">smalldatetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="80878-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="80878-114">삽입 시간 (이 경우에는 항목이 자리 표시자 일 수 있으므로 cmplType = 9의 미래입니다).</span><span class="sxs-lookup"><span data-stu-id="80878-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="80878-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="80878-115">cmplType</span></span>  <br/> |<span data-ttu-id="80878-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="80878-116">int, not null</span></span>  <br/> | <span data-ttu-id="80878-117">준수 이벤트 유형:</span><span class="sxs-lookup"><span data-stu-id="80878-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="80878-118">1: 채팅</span><span class="sxs-lookup"><span data-stu-id="80878-118">1: Chat</span></span> <br/>  <span data-ttu-id="80878-119">2: 백 채팅</span><span class="sxs-lookup"><span data-stu-id="80878-119">2: Backchat</span></span> <br/>  <span data-ttu-id="80878-120">3: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="80878-120">3: File download</span></span> <br/>  <span data-ttu-id="80878-121">4: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="80878-121">4: File upload</span></span> <br/>  <span data-ttu-id="80878-122">9: Provisional 파일 전송</span><span class="sxs-lookup"><span data-stu-id="80878-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="80878-123">10: 채팅 삭제 (바꾸기 사용)</span><span class="sxs-lookup"><span data-stu-id="80878-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="80878-124">11: 채팅 제거</span><span class="sxs-lookup"><span data-stu-id="80878-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="80878-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="80878-125">cmplTime</span></span>  <br/> |<span data-ttu-id="80878-126">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="80878-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="80878-127">이벤트에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="80878-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="80878-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="80878-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="80878-129">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="80878-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="80878-130">채널 URI (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="80878-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="80878-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="80878-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="80878-132">bigint</span><span class="sxs-lookup"><span data-stu-id="80878-132">bigint</span></span>  <br/> |<span data-ttu-id="80878-133">채팅 ID (chatId 테이블에 해당).</span><span class="sxs-lookup"><span data-stu-id="80878-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="80878-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="80878-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="80878-135">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="80878-135">int, not null</span></span>  <br/> |<span data-ttu-id="80878-136">포스터의 Principal ID (tblPrincipal 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="80878-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="80878-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="80878-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="80878-138">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="80878-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="80878-139">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="80878-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="80878-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="80878-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="80878-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="80878-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="80878-142">메시지 (인코딩은 cmplType에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="80878-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="80878-143">**키**</span><span class="sxs-lookup"><span data-stu-id="80878-143">**Key**</span></span>

|<span data-ttu-id="80878-144">**열**</span><span class="sxs-lookup"><span data-stu-id="80878-144">**Column**</span></span>|<span data-ttu-id="80878-145">**설명**</span><span class="sxs-lookup"><span data-stu-id="80878-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80878-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="80878-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="80878-147">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="80878-147">Primary key.</span></span>  <br/> |
   

