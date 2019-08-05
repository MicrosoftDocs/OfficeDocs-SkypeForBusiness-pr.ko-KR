---
title: FileTransfers 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196748"
---
# <a name="filetransfers-view"></a><span data-ttu-id="26fb4-104">FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="26fb4-104">FileTransfers view</span></span>
 
<span data-ttu-id="26fb4-105">FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="26fb4-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26fb4-107">FileTransfers 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="26fb4-108">**열**</span><span class="sxs-lookup"><span data-stu-id="26fb4-108">**Column**</span></span>|<span data-ttu-id="26fb4-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="26fb4-109">**Data Type**</span></span>|<span data-ttu-id="26fb4-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="26fb4-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26fb4-111">**이름이**</span><span class="sxs-lookup"><span data-stu-id="26fb4-111">**FileName**</span></span> <br/> |<span data-ttu-id="26fb4-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26fb4-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="26fb4-113">전송 된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="26fb4-114">**쿠키란**</span><span class="sxs-lookup"><span data-stu-id="26fb4-114">**Cookie**</span></span> <br/> |<span data-ttu-id="26fb4-115">name</span><span class="sxs-lookup"><span data-stu-id="26fb4-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="26fb4-116">모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="26fb4-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="26fb4-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="26fb4-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="26fb4-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="26fb4-119">동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="26fb4-120">**사항**</span><span class="sxs-lookup"><span data-stu-id="26fb4-120">**Accept**</span></span> <br/> |<span data-ttu-id="26fb4-121">다소</span><span class="sxs-lookup"><span data-stu-id="26fb4-121">bit</span></span>  <br/> |<span data-ttu-id="26fb4-122">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="26fb4-123">TRUE 인 경우 거부 및 취소는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="26fb4-124">**거부**</span><span class="sxs-lookup"><span data-stu-id="26fb4-124">**Reject**</span></span> <br/> |<span data-ttu-id="26fb4-125">다소</span><span class="sxs-lookup"><span data-stu-id="26fb4-125">bit</span></span>  <br/> |<span data-ttu-id="26fb4-126">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="26fb4-127">TRUE 이면 Accept와 Cancel은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="26fb4-128">**취소**</span><span class="sxs-lookup"><span data-stu-id="26fb4-128">**Cancel**</span></span> <br/> |<span data-ttu-id="26fb4-129">다소</span><span class="sxs-lookup"><span data-stu-id="26fb4-129">bit</span></span>  <br/> |<span data-ttu-id="26fb4-130">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="26fb4-131">TRUE 이면 Accept 및 Reject는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="26fb4-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

