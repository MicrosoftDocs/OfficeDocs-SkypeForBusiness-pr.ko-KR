---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809748"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="5e051-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="5e051-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="5e051-104">tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="5e051-105">**열**</span><span class="sxs-lookup"><span data-stu-id="5e051-105">**Columns**</span></span>

|<span data-ttu-id="5e051-106">**열**</span><span class="sxs-lookup"><span data-stu-id="5e051-106">**Column**</span></span>|<span data-ttu-id="5e051-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="5e051-107">**Type**</span></span>|<span data-ttu-id="5e051-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="5e051-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e051-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="5e051-109">channelUri</span></span>  <br/> |<span data-ttu-id="5e051-110">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e051-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5e051-111">채널 URI(Uniform Resource Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="5e051-112">userId</span><span class="sxs-lookup"><span data-stu-id="5e051-112">userId</span></span>  <br/> |<span data-ttu-id="5e051-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e051-113">int, not null</span></span>  <br/> |<span data-ttu-id="5e051-114">참가자의 계정 ID(tblPrincipal.prinID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="5e051-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="5e051-115">joinedAt</span></span>  <br/> |<span data-ttu-id="5e051-116">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e051-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="5e051-117">참가 이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="5e051-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="5e051-118">partedAt</span></span>  <br/> |<span data-ttu-id="5e051-119">bigint</span><span class="sxs-lookup"><span data-stu-id="5e051-119">bigint</span></span>  <br/> |<span data-ttu-id="5e051-p101">참가자가 아직 참가된 상태이면 Null입니다. Null이 아닌 경우 채널 나가기 이벤트의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="5e051-122">모든 변환기에서 이벤트를 처리하면 이러한 항목이 결국 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="5e051-123">userUri</span><span class="sxs-lookup"><span data-stu-id="5e051-123">userUri</span></span>  <br/> |<span data-ttu-id="5e051-124">nvarchar(255), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5e051-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="5e051-125">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="5e051-126">serverID</span><span class="sxs-lookup"><span data-stu-id="5e051-126">serverID</span></span>  <br/> |<span data-ttu-id="5e051-127">int</span><span class="sxs-lookup"><span data-stu-id="5e051-127">int</span></span>  <br/> |<span data-ttu-id="5e051-128">서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="5e051-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="5e051-129">sessionId</span></span>  <br/> |<span data-ttu-id="5e051-130">bigint</span><span class="sxs-lookup"><span data-stu-id="5e051-130">bigint</span></span>  <br/> |<span data-ttu-id="5e051-p102">서버 세션입니다. 이 값은 채팅 서비스가 시작할 때마다 생성되는 임의의 숫자입니다. 고립된 참가자를 식별하기 위한 목적으로 세션을 구분하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="5e051-134">**키**</span><span class="sxs-lookup"><span data-stu-id="5e051-134">**Key**</span></span>

|<span data-ttu-id="5e051-135">**열**</span><span class="sxs-lookup"><span data-stu-id="5e051-135">**Column**</span></span>|<span data-ttu-id="5e051-136">**설명**</span><span class="sxs-lookup"><span data-stu-id="5e051-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="5e051-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5e051-137">Primary key.</span></span>  <br/> |
   

