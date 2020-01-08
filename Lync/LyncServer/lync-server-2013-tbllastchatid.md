---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="81319-102">Lync Server 2013의 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="81319-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81319-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="81319-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="81319-104">tblLastChatId에는 각 사용자에 대해 생성 된 마지막 채팅 ID (및 tblChat 테이블에 사용 됨)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81319-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="81319-105">열</span><span class="sxs-lookup"><span data-stu-id="81319-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81319-106">열</span><span class="sxs-lookup"><span data-stu-id="81319-106">Column</span></span></th>
<th><span data-ttu-id="81319-107">유형</span><span class="sxs-lookup"><span data-stu-id="81319-107">Type</span></span></th>
<th><span data-ttu-id="81319-108">설명</span><span class="sxs-lookup"><span data-stu-id="81319-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81319-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="81319-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="81319-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="81319-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81319-111">노드 ID (채팅방에만 입력 하세요).</span><span class="sxs-lookup"><span data-stu-id="81319-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81319-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="81319-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="81319-113">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="81319-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="81319-114">마지막으로 사용한 채팅 ID.</span><span class="sxs-lookup"><span data-stu-id="81319-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="81319-115">핵심</span><span class="sxs-lookup"><span data-stu-id="81319-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81319-116">열</span><span class="sxs-lookup"><span data-stu-id="81319-116">Column</span></span></th>
<th><span data-ttu-id="81319-117">설명</span><span class="sxs-lookup"><span data-stu-id="81319-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81319-118">&lt;nodeID, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="81319-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="81319-119">기본 키 (nodeID만 처리에 충분 합니다.)</span><span class="sxs-lookup"><span data-stu-id="81319-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81319-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="81319-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="81319-121">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="81319-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="81319-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81319-122">See Also</span></span>


[<span data-ttu-id="81319-123">Lync Server 2013의 tblChat</span><span class="sxs-lookup"><span data-stu-id="81319-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

