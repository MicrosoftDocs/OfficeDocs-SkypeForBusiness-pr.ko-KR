---
title: 'Lync Server 2013: tblLastChatId'
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
ms.openlocfilehash: be10514a933cb6a311d115fbbb011398f2758ef9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="c9ce2-102">Lync Server 2013의 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="c9ce2-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ce2-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c9ce2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c9ce2-104">tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce2-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="c9ce2-105">단</span><span class="sxs-lookup"><span data-stu-id="c9ce2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9ce2-106">열</span><span class="sxs-lookup"><span data-stu-id="c9ce2-106">Column</span></span></th>
<th><span data-ttu-id="c9ce2-107">형식</span><span class="sxs-lookup"><span data-stu-id="c9ce2-107">Type</span></span></th>
<th><span data-ttu-id="c9ce2-108">설명</span><span class="sxs-lookup"><span data-stu-id="c9ce2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9ce2-109">입니다</span><span class="sxs-lookup"><span data-stu-id="c9ce2-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c9ce2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-111">노드 ID(대화방 유형 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce2-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9ce2-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="c9ce2-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-113">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c9ce2-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-114">마지막으로 사용된 채팅 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce2-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c9ce2-115">키</span><span class="sxs-lookup"><span data-stu-id="c9ce2-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9ce2-116">열</span><span class="sxs-lookup"><span data-stu-id="c9ce2-116">Column</span></span></th>
<th><span data-ttu-id="c9ce2-117">설명</span><span class="sxs-lookup"><span data-stu-id="c9ce2-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9ce2-118">&lt;입니다, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="c9ce2-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-119">기본 키(처리를 위해서는 nodeID만으로도 충분함)입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce2-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9ce2-120">입니다</span><span class="sxs-lookup"><span data-stu-id="c9ce2-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c9ce2-121">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce2-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c9ce2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9ce2-122">See Also</span></span>


[<span data-ttu-id="c9ce2-123">Lync Server 2013의 tblChat</span><span class="sxs-lookup"><span data-stu-id="c9ce2-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

