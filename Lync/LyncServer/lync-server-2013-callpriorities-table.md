---
title: 'Lync Server 2013: CallPriorities 순위 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b44b48cbe23ae004211e4ca6f29b1afc434af1e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514835"
---
# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="510fb-102">Lync Server 2013의 CallPriorities 순위 테이블</span><span class="sxs-lookup"><span data-stu-id="510fb-102">CallPriorities table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="510fb-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="510fb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="510fb-104">CallPriorities 테이블은 '응급', '긴급' 또는 '보통'과 같은 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="510fb-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="510fb-105">열</span><span class="sxs-lookup"><span data-stu-id="510fb-105">Column</span></span></th>
<th><span data-ttu-id="510fb-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="510fb-106">Data Type</span></span></th>
<th><span data-ttu-id="510fb-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="510fb-107">Key/Index</span></span></th>
<th><span data-ttu-id="510fb-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="510fb-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="510fb-109"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="510fb-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="510fb-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="510fb-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="510fb-111">Primary</span><span class="sxs-lookup"><span data-stu-id="510fb-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510fb-112"><strong>우선 순위</strong></span><span class="sxs-lookup"><span data-stu-id="510fb-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="510fb-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="510fb-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="510fb-114">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="510fb-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="510fb-115">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="510fb-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="510fb-116">1 - 일반</span><span class="sxs-lookup"><span data-stu-id="510fb-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="510fb-117">2 - 보통</span><span class="sxs-lookup"><span data-stu-id="510fb-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="510fb-118">3 - 긴급</span><span class="sxs-lookup"><span data-stu-id="510fb-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="510fb-119">4 - 응급</span><span class="sxs-lookup"><span data-stu-id="510fb-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

