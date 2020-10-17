---
title: 'Lync Server 2013: tblLastChatId'
description: 'Lync Server 2013: tblLastChatId.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547604"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="4f6d9-103">Lync Server 2013의 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="4f6d9-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f6d9-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4f6d9-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4f6d9-105">tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f6d9-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="4f6d9-106">단</span><span class="sxs-lookup"><span data-stu-id="4f6d9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f6d9-107">열</span><span class="sxs-lookup"><span data-stu-id="4f6d9-107">Column</span></span></th>
<th><span data-ttu-id="4f6d9-108">유형</span><span class="sxs-lookup"><span data-stu-id="4f6d9-108">Type</span></span></th>
<th><span data-ttu-id="4f6d9-109">설명</span><span class="sxs-lookup"><span data-stu-id="4f6d9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f6d9-110">입니다</span><span class="sxs-lookup"><span data-stu-id="4f6d9-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f6d9-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-112">노드 ID(대화방 유형 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f6d9-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f6d9-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="4f6d9-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-114">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f6d9-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-115">마지막으로 사용된 채팅 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4f6d9-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4f6d9-116">키</span><span class="sxs-lookup"><span data-stu-id="4f6d9-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f6d9-117">열</span><span class="sxs-lookup"><span data-stu-id="4f6d9-117">Column</span></span></th>
<th><span data-ttu-id="4f6d9-118">설명</span><span class="sxs-lookup"><span data-stu-id="4f6d9-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f6d9-119">&lt;입니다, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="4f6d9-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-120">기본 키(처리를 위해서는 nodeID만으로도 충분함)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f6d9-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f6d9-121">입니다</span><span class="sxs-lookup"><span data-stu-id="4f6d9-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4f6d9-122">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4f6d9-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4f6d9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f6d9-123">See Also</span></span>


[<span data-ttu-id="4f6d9-124">Lync Server 2013의 tblChat</span><span class="sxs-lookup"><span data-stu-id="4f6d9-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

