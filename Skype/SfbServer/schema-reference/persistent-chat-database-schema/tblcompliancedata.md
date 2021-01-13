---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809858"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="9dd1e-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="9dd1e-103">tblComplianceData</span></span>
 
<span data-ttu-id="9dd1e-104">tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="9dd1e-105">**열**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-105">**Columns**</span></span>

|<span data-ttu-id="9dd1e-106">**열**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-106">**Column**</span></span>|<span data-ttu-id="9dd1e-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-107">**Type**</span></span>|<span data-ttu-id="9dd1e-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9dd1e-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="9dd1e-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="9dd1e-110">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="9dd1e-111">이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="9dd1e-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="9dd1e-112">entryDate</span></span>  <br/> |<span data-ttu-id="9dd1e-113">smalldatetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="9dd1e-114">삽입 시간(cmplType=9의 경우에는 항목이 단순히 자리 표시자이므로 오랜 시간 후일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="9dd1e-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="9dd1e-115">cmplType</span></span>  <br/> |<span data-ttu-id="9dd1e-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-116">int, not null</span></span>  <br/> | <span data-ttu-id="9dd1e-117">준수 이벤트 유형:</span><span class="sxs-lookup"><span data-stu-id="9dd1e-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="9dd1e-118">1: 채팅</span><span class="sxs-lookup"><span data-stu-id="9dd1e-118">1: Chat</span></span> <br/>  <span data-ttu-id="9dd1e-119">2: 백채트</span><span class="sxs-lookup"><span data-stu-id="9dd1e-119">2: Backchat</span></span> <br/>  <span data-ttu-id="9dd1e-120">3: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="9dd1e-120">3: File download</span></span> <br/>  <span data-ttu-id="9dd1e-121">4: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="9dd1e-121">4: File upload</span></span> <br/>  <span data-ttu-id="9dd1e-122">9: 임시 파일 전송</span><span class="sxs-lookup"><span data-stu-id="9dd1e-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="9dd1e-123">10: 채팅 삭제(바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="9dd1e-124">11: 채팅 삭제</span><span class="sxs-lookup"><span data-stu-id="9dd1e-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="9dd1e-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="9dd1e-125">cmplTime</span></span>  <br/> |<span data-ttu-id="9dd1e-126">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="9dd1e-127">이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="9dd1e-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="9dd1e-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="9dd1e-129">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="9dd1e-130">채널 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="9dd1e-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="9dd1e-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="9dd1e-132">bigint</span><span class="sxs-lookup"><span data-stu-id="9dd1e-132">bigint</span></span>  <br/> |<span data-ttu-id="9dd1e-133">채팅 ID(tblChat.chatId 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="9dd1e-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="9dd1e-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="9dd1e-135">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-135">int, not null</span></span>  <br/> |<span data-ttu-id="9dd1e-136">게시자의 사용자 ID(tblPrincipal.prinID 테이블에 해당됨)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="9dd1e-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="9dd1e-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="9dd1e-138">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="9dd1e-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="9dd1e-139">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="9dd1e-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="9dd1e-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="9dd1e-141">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="9dd1e-142">메시지(인코딩은 cmplType에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="9dd1e-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="9dd1e-143">**키**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-143">**Key**</span></span>

|<span data-ttu-id="9dd1e-144">**열**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-144">**Column**</span></span>|<span data-ttu-id="9dd1e-145">**설명**</span><span class="sxs-lookup"><span data-stu-id="9dd1e-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9dd1e-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="9dd1e-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="9dd1e-147">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd1e-147">Primary key.</span></span>  <br/> |
   

