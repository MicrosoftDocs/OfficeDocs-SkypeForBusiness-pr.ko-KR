---
title: 'Lync Server 2013: 위치 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accab39d1f1f7cb1855ba651ea217aa3b0a4bd8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="ec3bd-102">Lync Server 2013의 위치 테이블</span><span class="sxs-lookup"><span data-stu-id="ec3bd-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec3bd-103">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ec3bd-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ec3bd-104">각 레코드는 E9-1-1 통화와 같은 응급 통화에서 하나의 위치 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec3bd-105">열</span><span class="sxs-lookup"><span data-stu-id="ec3bd-105">Column</span></span></th>
<th><span data-ttu-id="ec3bd-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec3bd-106">Data Type</span></span></th>
<th><span data-ttu-id="ec3bd-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ec3bd-107">Key/Index</span></span></th>
<th><span data-ttu-id="ec3bd-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ec3bd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec3bd-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ec3bd-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3bd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ec3bd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec3bd-111">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="ec3bd-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec3bd-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-112">Time of session request.</span></span> <span data-ttu-id="ec3bd-113"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ec3bd-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec3bd-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ec3bd-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3bd-116">int</span><span class="sxs-lookup"><span data-stu-id="ec3bd-116">int</span></span></p></td>
<td><p><span data-ttu-id="ec3bd-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="ec3bd-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec3bd-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-118">ID number to identify the session.</span></span> <span data-ttu-id="ec3bd-119"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ec3bd-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec3bd-121"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="ec3bd-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3bd-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ec3bd-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec3bd-123">응급 통화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ec3bd-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

