---
title: 'Lync Server 2013: tblActivePeers'
description: 'Lync Server 2013: tblActivePeers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f274f82a280883e38e8e02409305982b64c18e4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573744"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="62e34-103">Lync Server 2013의 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="62e34-103">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e34-104">_**마지막으로 수정 된 항목:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="62e34-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="62e34-105">tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-105">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="62e34-106">단</span><span class="sxs-lookup"><span data-stu-id="62e34-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62e34-107">열</span><span class="sxs-lookup"><span data-stu-id="62e34-107">Column</span></span></th>
<th><span data-ttu-id="62e34-108">유형</span><span class="sxs-lookup"><span data-stu-id="62e34-108">Type</span></span></th>
<th><span data-ttu-id="62e34-109">설명</span><span class="sxs-lookup"><span data-stu-id="62e34-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e34-110">aplServerID</span><span class="sxs-lookup"><span data-stu-id="62e34-110">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="62e34-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="62e34-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="62e34-112">항목을 게시 한 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-112">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e34-113">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="62e34-113">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="62e34-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="62e34-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="62e34-115">게시 서버가 연결 된 피어의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-115">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="62e34-116">키</span><span class="sxs-lookup"><span data-stu-id="62e34-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62e34-117">열</span><span class="sxs-lookup"><span data-stu-id="62e34-117">Column</span></span></th>
<th><span data-ttu-id="62e34-118">설명</span><span class="sxs-lookup"><span data-stu-id="62e34-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e34-119">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="62e34-119">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="62e34-120">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e34-121">aplServerID</span><span class="sxs-lookup"><span data-stu-id="62e34-121">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="62e34-122">TblServerIdentity 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e34-123">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="62e34-123">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="62e34-124">TblServerIdentity 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="62e34-124">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

