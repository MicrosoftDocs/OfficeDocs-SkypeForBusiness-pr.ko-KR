---
title: 'Lync Server 2013: tblActivePeers'
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
ms.openlocfilehash: 8a47ac4368dd424b08cfb47c6d867bc20144e45c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="a96e8-102">Lync Server 2013의 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="a96e8-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a96e8-103">_**마지막으로 수정 된 항목:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="a96e8-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="a96e8-104">tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="a96e8-105">단</span><span class="sxs-lookup"><span data-stu-id="a96e8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96e8-106">열</span><span class="sxs-lookup"><span data-stu-id="a96e8-106">Column</span></span></th>
<th><span data-ttu-id="a96e8-107">형식</span><span class="sxs-lookup"><span data-stu-id="a96e8-107">Type</span></span></th>
<th><span data-ttu-id="a96e8-108">설명</span><span class="sxs-lookup"><span data-stu-id="a96e8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96e8-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a96e8-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="a96e8-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="a96e8-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a96e8-111">항목을 게시 한 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96e8-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a96e8-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="a96e8-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="a96e8-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a96e8-114">게시 서버가 연결 된 피어의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a96e8-115">키</span><span class="sxs-lookup"><span data-stu-id="a96e8-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96e8-116">열</span><span class="sxs-lookup"><span data-stu-id="a96e8-116">Column</span></span></th>
<th><span data-ttu-id="a96e8-117">설명</span><span class="sxs-lookup"><span data-stu-id="a96e8-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96e8-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="a96e8-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a96e8-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96e8-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a96e8-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="a96e8-121">TblServerIdentity 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96e8-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a96e8-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="a96e8-123">TblServerIdentity 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a96e8-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

