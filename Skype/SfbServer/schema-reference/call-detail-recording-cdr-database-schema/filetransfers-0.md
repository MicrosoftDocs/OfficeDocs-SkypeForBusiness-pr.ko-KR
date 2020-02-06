---
title: 비즈니스용 Skype 서버 2015의 FileTransfers 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 각 레코드는 하나의 파일 전송 세션을 나타냅니다.
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815216"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="da899-103">비즈니스용 Skype 서버 2015의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="da899-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="da899-104">각 레코드는 하나의 파일 전송 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da899-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="da899-105">**열**</span><span class="sxs-lookup"><span data-stu-id="da899-105">**Column**</span></span>|<span data-ttu-id="da899-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="da899-106">**Data Type**</span></span>|<span data-ttu-id="da899-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="da899-107">**Key/Index**</span></span>|<span data-ttu-id="da899-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="da899-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da899-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="da899-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="da899-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="da899-110">datetime</span></span>  <br/> |<span data-ttu-id="da899-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="da899-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="da899-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-112">Time of session request.</span></span> <span data-ttu-id="da899-113">세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da899-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="da899-114">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da899-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="da899-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="da899-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="da899-116">int</span><span class="sxs-lookup"><span data-stu-id="da899-116">int</span></span>  <br/> |<span data-ttu-id="da899-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="da899-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="da899-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-118">ID number to identify the session.</span></span> <span data-ttu-id="da899-119">세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da899-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="da899-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da899-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="da899-121">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="da899-121">**File Name**</span></span> <br/> |<span data-ttu-id="da899-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="da899-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="da899-123">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="da899-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="da899-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="da899-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="da899-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="da899-126">동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="da899-127">**쿠키란**</span><span class="sxs-lookup"><span data-stu-id="da899-127">**Cookie**</span></span> <br/> |<span data-ttu-id="da899-128">name</span><span class="sxs-lookup"><span data-stu-id="da899-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="da899-129">주요한</span><span class="sxs-lookup"><span data-stu-id="da899-129">Primary</span></span>  <br/> |<span data-ttu-id="da899-130">모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da899-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="da899-131">**사항**</span><span class="sxs-lookup"><span data-stu-id="da899-131">**Accept**</span></span> <br/> |<span data-ttu-id="da899-132">다소</span><span class="sxs-lookup"><span data-stu-id="da899-132">bit</span></span>  <br/> ||<span data-ttu-id="da899-133">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da899-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="da899-134">TRUE 인 경우 거부 및 취소는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-134">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="da899-135">**거부**</span><span class="sxs-lookup"><span data-stu-id="da899-135">**Reject**</span></span> <br/> |<span data-ttu-id="da899-136">다소</span><span class="sxs-lookup"><span data-stu-id="da899-136">bit</span></span>  <br/> ||<span data-ttu-id="da899-137">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da899-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="da899-138">TRUE 이면 Accept와 Cancel은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-138">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="da899-139">**취소**</span><span class="sxs-lookup"><span data-stu-id="da899-139">**Cancel**</span></span> <br/> |<span data-ttu-id="da899-140">다소</span><span class="sxs-lookup"><span data-stu-id="da899-140">bit</span></span>  <br/> ||<span data-ttu-id="da899-141">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da899-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="da899-142">TRUE 이면 Accept 및 Reject는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="da899-142">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="da899-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="da899-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="da899-144">Dmtf</span><span class="sxs-lookup"><span data-stu-id="da899-144">Datetime</span></span>  <br/> ||<span data-ttu-id="da899-145">모니터링 서비스에 내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da899-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="da899-146">이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="da899-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

