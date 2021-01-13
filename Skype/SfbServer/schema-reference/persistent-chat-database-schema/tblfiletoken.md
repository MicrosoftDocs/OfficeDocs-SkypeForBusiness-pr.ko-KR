---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816018"
---
# <a name="tblfiletoken"></a><span data-ttu-id="db816-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="db816-103">tblFileToken</span></span>
 
<span data-ttu-id="db816-104">tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="db816-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="db816-105">**열**</span><span class="sxs-lookup"><span data-stu-id="db816-105">**Columns**</span></span>

|<span data-ttu-id="db816-106">**열**</span><span class="sxs-lookup"><span data-stu-id="db816-106">**Column**</span></span>|<span data-ttu-id="db816-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="db816-107">**Type**</span></span>|<span data-ttu-id="db816-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="db816-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db816-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="db816-109">fileToken</span></span>  <br/> |<span data-ttu-id="db816-110">nvarchar(50), null이 아님</span><span class="sxs-lookup"><span data-stu-id="db816-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="db816-111">고유한 토큰(GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="db816-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="db816-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="db816-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="db816-113">int, not null</span></span>  <br/> |<span data-ttu-id="db816-114">파일을 전송 중인 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="db816-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="db816-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="db816-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="db816-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="db816-117">대화방 노드의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="db816-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="db816-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="db816-119">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="db816-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="db816-p101">만료 시간입니다. 고정되지 않은 한 토큰이 30분 후 만료됩니다(이 열의 다음 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="db816-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="db816-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="db816-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="db816-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db816-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="db816-124">전송된 파일의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="db816-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="db816-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="db816-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="db816-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db816-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="db816-127">전송된 파일에 대한 축소판 그림의 URL입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="db816-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="db816-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="db816-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="db816-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="db816-129">datetime2</span></span>  <br/> |<span data-ttu-id="db816-130">실제 파일 전송 작업의 타임스탬프입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="db816-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="db816-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="db816-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="db816-132">bit</span><span class="sxs-lookup"><span data-stu-id="db816-132">bit</span></span>  <br/> |<span data-ttu-id="db816-133">업로드인 경우 True, 다운로드인 경우 False입니다(준수 서비스용).</span><span class="sxs-lookup"><span data-stu-id="db816-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="db816-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="db816-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="db816-135">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="db816-135">bit, not null</span></span>  <br/> |<span data-ttu-id="db816-136">토큰이 고정된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-136">True if token is pinned.</span></span> <span data-ttu-id="db816-137">Compliance Service에서 관련 필드를 검색할 수 있는 기회가 제공될 때까지 테이블에 토큰을 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db816-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="db816-138">**키**</span><span class="sxs-lookup"><span data-stu-id="db816-138">**Keys**</span></span>

|<span data-ttu-id="db816-139">**열**</span><span class="sxs-lookup"><span data-stu-id="db816-139">**Column**</span></span>|<span data-ttu-id="db816-140">**설명**</span><span class="sxs-lookup"><span data-stu-id="db816-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db816-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="db816-141">fileToken</span></span>  <br/> |<span data-ttu-id="db816-142">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="db816-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="db816-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="db816-144">tblNode.nodeGuid 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="db816-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

