---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816008"
---
# <a name="tbllastchatid"></a><span data-ttu-id="af02b-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="af02b-103">tblLastChatId</span></span>
 
<span data-ttu-id="af02b-104">tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af02b-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="af02b-105">**열**</span><span class="sxs-lookup"><span data-stu-id="af02b-105">**Columns**</span></span>

|<span data-ttu-id="af02b-106">**열**</span><span class="sxs-lookup"><span data-stu-id="af02b-106">**Column**</span></span>|<span data-ttu-id="af02b-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="af02b-107">**Type**</span></span>|<span data-ttu-id="af02b-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="af02b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af02b-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="af02b-109">nodeID</span></span>  <br/> |<span data-ttu-id="af02b-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="af02b-110">int, not null</span></span>  <br/> |<span data-ttu-id="af02b-111">노드 ID(대화방 유형 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="af02b-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="af02b-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="af02b-112">lastChatID</span></span>  <br/> |<span data-ttu-id="af02b-113">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="af02b-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="af02b-114">마지막으로 사용된 채팅 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="af02b-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="af02b-115">**키**</span><span class="sxs-lookup"><span data-stu-id="af02b-115">**Keys**</span></span>

|<span data-ttu-id="af02b-116">**열**</span><span class="sxs-lookup"><span data-stu-id="af02b-116">**Column**</span></span>|<span data-ttu-id="af02b-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="af02b-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="af02b-118">기본 키(처리를 위해서는 nodeID만으로도 충분함)입니다.</span><span class="sxs-lookup"><span data-stu-id="af02b-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="af02b-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="af02b-119">nodeID</span></span>  <br/> |<span data-ttu-id="af02b-120">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="af02b-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="af02b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af02b-121">See also</span></span>

[<span data-ttu-id="af02b-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="af02b-122">tblChat</span></span>](tblchat.md)
