---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814646"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="ea8e8-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="ea8e8-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="ea8e8-104">tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="ea8e8-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-105">**Columns**</span></span>

|<span data-ttu-id="ea8e8-106">**열**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-106">**Column**</span></span>|<span data-ttu-id="ea8e8-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-107">**Type**</span></span>|<span data-ttu-id="ea8e8-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea8e8-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="ea8e8-109">channelUri</span></span>  <br/> |<span data-ttu-id="ea8e8-110">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="ea8e8-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ea8e8-111">채널 URI (Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ea8e8-112">userId</span><span class="sxs-lookup"><span data-stu-id="ea8e8-112">userId</span></span>  <br/> |<span data-ttu-id="ea8e8-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="ea8e8-113">int, not null</span></span>  <br/> |<span data-ttu-id="ea8e8-114">참가자의 사용자 ID (tblPrincipal 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="ea8e8-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ea8e8-115">에서 joinedAt</span><span class="sxs-lookup"><span data-stu-id="ea8e8-115">joinedAt</span></span>  <br/> |<span data-ttu-id="ea8e8-116">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ea8e8-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="ea8e8-117">참가 이벤트의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="ea8e8-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="ea8e8-118">partedAt</span></span>  <br/> |<span data-ttu-id="ea8e8-119">bigint</span><span class="sxs-lookup"><span data-stu-id="ea8e8-119">bigint</span></span>  <br/> |<span data-ttu-id="ea8e8-120">참가자가 아직 참가 한 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-120">Null if participant is still joined.</span></span> <span data-ttu-id="ea8e8-121">Null이 아닌 경우 이벤트를 종료 하는 채널의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="ea8e8-122">이러한 항목은 모든 번역기가 이벤트를 처리할 때 결국 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="ea8e8-123">userUri</span><span class="sxs-lookup"><span data-stu-id="ea8e8-123">userUri</span></span>  <br/> |<span data-ttu-id="ea8e8-124">nvarchar (255), null 아님</span><span class="sxs-lookup"><span data-stu-id="ea8e8-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="ea8e8-125">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="ea8e8-126">serverID</span><span class="sxs-lookup"><span data-stu-id="ea8e8-126">serverID</span></span>  <br/> |<span data-ttu-id="ea8e8-127">int</span><span class="sxs-lookup"><span data-stu-id="ea8e8-127">int</span></span>  <br/> |<span data-ttu-id="ea8e8-128">서버 id (tblServerIdentity 테이블에 해당)</span><span class="sxs-lookup"><span data-stu-id="ea8e8-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="ea8e8-129">Session</span><span class="sxs-lookup"><span data-stu-id="ea8e8-129">sessionId</span></span>  <br/> |<span data-ttu-id="ea8e8-130">bigint</span><span class="sxs-lookup"><span data-stu-id="ea8e8-130">bigint</span></span>  <br/> |<span data-ttu-id="ea8e8-131">서버 세션.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-131">Server session.</span></span> <span data-ttu-id="ea8e8-132">채팅 서비스를 시작할 때마다 생성 되는 난수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="ea8e8-133">고아 참가자를 식별 하기 위해 세션을 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="ea8e8-134">**키**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-134">**Key**</span></span>

|<span data-ttu-id="ea8e8-135">**열**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-135">**Column**</span></span>|<span data-ttu-id="ea8e8-136">**설명**</span><span class="sxs-lookup"><span data-stu-id="ea8e8-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea8e8-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="ea8e8-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="ea8e8-138">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e8-138">Primary key.</span></span>  <br/> |
   

