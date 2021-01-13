---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함되어 있습니다.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812938"
---
# <a name="tblactivepeers"></a><span data-ttu-id="0c6bb-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="0c6bb-103">tblActivePeers</span></span>
 
<span data-ttu-id="0c6bb-104">tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="0c6bb-105">**열**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-105">**Columns**</span></span>

|<span data-ttu-id="0c6bb-106">**열**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-106">**Column**</span></span>|<span data-ttu-id="0c6bb-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-107">**Type**</span></span>|<span data-ttu-id="0c6bb-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c6bb-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="0c6bb-109">aplServerID</span></span>  <br/> |<span data-ttu-id="0c6bb-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0c6bb-110">int, not null</span></span>  <br/> |<span data-ttu-id="0c6bb-111">항목을 게시한 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="0c6bb-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="0c6bb-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="0c6bb-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0c6bb-113">int, not null</span></span>  <br/> |<span data-ttu-id="0c6bb-114">게시 서버가 연결된 피어의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="0c6bb-115">**키**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-115">**Keys**</span></span>

|<span data-ttu-id="0c6bb-116">**열**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-116">**Column**</span></span>|<span data-ttu-id="0c6bb-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="0c6bb-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="0c6bb-118">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0c6bb-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="0c6bb-119">aplServerID</span></span>  <br/> |<span data-ttu-id="0c6bb-120">tblServerIdentity.serverID 테이블에서 lookup이 있는 외장 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="0c6bb-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="0c6bb-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="0c6bb-122">tblServerIdentity.serverID 테이블에서 lookup이 있는 외장 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0c6bb-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

