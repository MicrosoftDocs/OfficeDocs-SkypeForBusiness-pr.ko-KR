---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814716"
---
# <a name="tblactivepeers"></a><span data-ttu-id="abdd5-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="abdd5-103">tblActivePeers</span></span>
 
<span data-ttu-id="abdd5-104">tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="abdd5-105">**열**</span><span class="sxs-lookup"><span data-stu-id="abdd5-105">**Columns**</span></span>

|<span data-ttu-id="abdd5-106">**열**</span><span class="sxs-lookup"><span data-stu-id="abdd5-106">**Column**</span></span>|<span data-ttu-id="abdd5-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="abdd5-107">**Type**</span></span>|<span data-ttu-id="abdd5-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="abdd5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abdd5-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="abdd5-109">aplServerID</span></span>  <br/> |<span data-ttu-id="abdd5-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="abdd5-110">int, not null</span></span>  <br/> |<span data-ttu-id="abdd5-111">항목을 게시 한 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="abdd5-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="abdd5-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="abdd5-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="abdd5-113">int, not null</span></span>  <br/> |<span data-ttu-id="abdd5-114">게시 서버가 연결 된 피어의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="abdd5-115">**핵심**</span><span class="sxs-lookup"><span data-stu-id="abdd5-115">**Keys**</span></span>

|<span data-ttu-id="abdd5-116">**열**</span><span class="sxs-lookup"><span data-stu-id="abdd5-116">**Column**</span></span>|<span data-ttu-id="abdd5-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="abdd5-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abdd5-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="abdd5-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="abdd5-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="abdd5-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="abdd5-120">aplServerID</span></span>  <br/> |<span data-ttu-id="abdd5-121">TblServerIdentity 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="abdd5-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="abdd5-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="abdd5-123">TblServerIdentity 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

