---
title: 비즈니스용 Skype 서버의 FileTransfers 테이블
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
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 각 레코드는 하나의 파일 전송 세션을 나타냅니다.
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821698"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="eb318-103">비즈니스용 Skype 서버의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="eb318-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb318-104">각 레코드는 하나의 파일 전송 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="eb318-105">**열**</span><span class="sxs-lookup"><span data-stu-id="eb318-105">**Column**</span></span>|<span data-ttu-id="eb318-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="eb318-106">**Data Type**</span></span>|<span data-ttu-id="eb318-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="eb318-107">**Key/Index**</span></span>|<span data-ttu-id="eb318-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="eb318-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb318-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="eb318-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="eb318-110">datetime</span><span class="sxs-lookup"><span data-stu-id="eb318-110">datetime</span></span>  <br/> |<span data-ttu-id="eb318-111">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="eb318-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="eb318-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-112">Time of session request.</span></span> <span data-ttu-id="eb318-113">**SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="eb318-114">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb318-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="eb318-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="eb318-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="eb318-116">int</span><span class="sxs-lookup"><span data-stu-id="eb318-116">int</span></span>  <br/> |<span data-ttu-id="eb318-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="eb318-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="eb318-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-118">ID number to identify the session.</span></span> <span data-ttu-id="eb318-119">**SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="eb318-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb318-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="eb318-121">**File Name**</span><span class="sxs-lookup"><span data-stu-id="eb318-121">**File Name**</span></span> <br/> |<span data-ttu-id="eb318-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="eb318-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="eb318-123">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="eb318-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="eb318-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="eb318-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="eb318-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="eb318-126">동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="eb318-127">**쿠키**</span><span class="sxs-lookup"><span data-stu-id="eb318-127">**Cookie**</span></span> <br/> |<span data-ttu-id="eb318-128">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="eb318-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="eb318-129">Primary</span><span class="sxs-lookup"><span data-stu-id="eb318-129">Primary</span></span>  <br/> |<span data-ttu-id="eb318-130">이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="eb318-131">**수락**</span><span class="sxs-lookup"><span data-stu-id="eb318-131">**Accept**</span></span> <br/> |<span data-ttu-id="eb318-132">bit</span><span class="sxs-lookup"><span data-stu-id="eb318-132">bit</span></span>  <br/> ||<span data-ttu-id="eb318-p103">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="eb318-135">**거부**</span><span class="sxs-lookup"><span data-stu-id="eb318-135">**Reject**</span></span> <br/> |<span data-ttu-id="eb318-136">bit</span><span class="sxs-lookup"><span data-stu-id="eb318-136">bit</span></span>  <br/> ||<span data-ttu-id="eb318-p104">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="eb318-139">**취소**</span><span class="sxs-lookup"><span data-stu-id="eb318-139">**Cancel**</span></span> <br/> |<span data-ttu-id="eb318-140">bit</span><span class="sxs-lookup"><span data-stu-id="eb318-140">bit</span></span>  <br/> ||<span data-ttu-id="eb318-p105">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="eb318-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="eb318-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="eb318-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="eb318-144">Datetime</span></span>  <br/> ||<span data-ttu-id="eb318-145">모니터링 서비스의 내부 사용 용도</span><span class="sxs-lookup"><span data-stu-id="eb318-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="eb318-146">이 필드는 비즈니스용 Skype 서버 2015에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="eb318-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

