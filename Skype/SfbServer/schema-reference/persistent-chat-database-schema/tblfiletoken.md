---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken에는 파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814596"
---
# <a name="tblfiletoken"></a><span data-ttu-id="f4c44-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="f4c44-103">tblFileToken</span></span>
 
<span data-ttu-id="f4c44-104">tblFileToken에는 파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="f4c44-105">**열**</span><span class="sxs-lookup"><span data-stu-id="f4c44-105">**Columns**</span></span>

|<span data-ttu-id="f4c44-106">**열**</span><span class="sxs-lookup"><span data-stu-id="f4c44-106">**Column**</span></span>|<span data-ttu-id="f4c44-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="f4c44-107">**Type**</span></span>|<span data-ttu-id="f4c44-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="f4c44-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4c44-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="f4c44-109">fileToken</span></span>  <br/> |<span data-ttu-id="f4c44-110">nvarchar (50), null 아님</span><span class="sxs-lookup"><span data-stu-id="f4c44-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="f4c44-111">고유 토큰 (GUID).</span><span class="sxs-lookup"><span data-stu-id="f4c44-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="f4c44-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="f4c44-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="f4c44-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="f4c44-113">int, not null</span></span>  <br/> |<span data-ttu-id="f4c44-114">파일을 전송 하는 주체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="f4c44-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="f4c44-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="f4c44-116">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="f4c44-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="f4c44-117">채팅방 노드의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="f4c44-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="f4c44-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="f4c44-119">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="f4c44-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="f4c44-120">만료 시간.</span><span class="sxs-lookup"><span data-stu-id="f4c44-120">Expiration time.</span></span> <span data-ttu-id="f4c44-121">(고정 되지 않는 한 30 분 후에 토큰이 만료 됩니다 (이 칼럼의 다음 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="f4c44-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="f4c44-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="f4c44-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="f4c44-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4c44-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4c44-124">전송 된 파일의 URL입니다 (준수 서비스 사용).</span><span class="sxs-lookup"><span data-stu-id="f4c44-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="f4c44-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="f4c44-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="f4c44-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f4c44-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4c44-127">전송 된 파일의 축소판 그림 URL입니다 (준수 서비스 사용).</span><span class="sxs-lookup"><span data-stu-id="f4c44-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="f4c44-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="f4c44-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="f4c44-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="f4c44-129">datetime2</span></span>  <br/> |<span data-ttu-id="f4c44-130">실제 파일 전송 작업 (준수 서비스 사용)에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="f4c44-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="f4c44-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="f4c44-132">다소</span><span class="sxs-lookup"><span data-stu-id="f4c44-132">bit</span></span>  <br/> |<span data-ttu-id="f4c44-133">업로드 하는 경우 True False 인 경우 (준수 서비스 사용)</span><span class="sxs-lookup"><span data-stu-id="f4c44-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="f4c44-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="f4c44-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="f4c44-135">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="f4c44-135">bit, not null</span></span>  <br/> |<span data-ttu-id="f4c44-136">토큰이 고정 되어 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-136">True if token is pinned.</span></span> <span data-ttu-id="f4c44-137">준수 서비스에서 관련 필드를 검색할 기회가 생길 때까지 테이블에 토큰을 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="f4c44-138">**핵심**</span><span class="sxs-lookup"><span data-stu-id="f4c44-138">**Keys**</span></span>

|<span data-ttu-id="f4c44-139">**열**</span><span class="sxs-lookup"><span data-stu-id="f4c44-139">**Column**</span></span>|<span data-ttu-id="f4c44-140">**설명**</span><span class="sxs-lookup"><span data-stu-id="f4c44-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4c44-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="f4c44-141">fileToken</span></span>  <br/> |<span data-ttu-id="f4c44-142">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f4c44-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="f4c44-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="f4c44-144">TblNode. nodeGuid 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c44-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

