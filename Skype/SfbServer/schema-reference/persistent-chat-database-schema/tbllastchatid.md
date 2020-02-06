---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId에는 각 사용자에 대해 생성 된 마지막 채팅 ID (및 tblChat 테이블에 사용 됨)가 포함 되어 있습니다.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814586"
---
# <a name="tbllastchatid"></a><span data-ttu-id="0dca1-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="0dca1-103">tblLastChatId</span></span>
 
<span data-ttu-id="0dca1-104">tblLastChatId에는 각 사용자에 대해 생성 된 마지막 채팅 ID (및 tblChat 테이블에 사용 됨)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dca1-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="0dca1-105">**열**</span><span class="sxs-lookup"><span data-stu-id="0dca1-105">**Columns**</span></span>

|<span data-ttu-id="0dca1-106">**열**</span><span class="sxs-lookup"><span data-stu-id="0dca1-106">**Column**</span></span>|<span data-ttu-id="0dca1-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="0dca1-107">**Type**</span></span>|<span data-ttu-id="0dca1-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="0dca1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0dca1-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="0dca1-109">nodeID</span></span>  <br/> |<span data-ttu-id="0dca1-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="0dca1-110">int, not null</span></span>  <br/> |<span data-ttu-id="0dca1-111">노드 ID (채팅방에만 입력 하세요).</span><span class="sxs-lookup"><span data-stu-id="0dca1-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="0dca1-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="0dca1-112">lastChatID</span></span>  <br/> |<span data-ttu-id="0dca1-113">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0dca1-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="0dca1-114">마지막으로 사용한 채팅 ID.</span><span class="sxs-lookup"><span data-stu-id="0dca1-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="0dca1-115">**핵심**</span><span class="sxs-lookup"><span data-stu-id="0dca1-115">**Keys**</span></span>

|<span data-ttu-id="0dca1-116">**열**</span><span class="sxs-lookup"><span data-stu-id="0dca1-116">**Column**</span></span>|<span data-ttu-id="0dca1-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="0dca1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0dca1-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="0dca1-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="0dca1-119">기본 키 (nodeID만 처리에 충분 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0dca1-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="0dca1-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="0dca1-120">nodeID</span></span>  <br/> |<span data-ttu-id="0dca1-121">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0dca1-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0dca1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dca1-122">See also</span></span>

[<span data-ttu-id="0dca1-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="0dca1-123">tblChat</span></span>](tblchat.md)
