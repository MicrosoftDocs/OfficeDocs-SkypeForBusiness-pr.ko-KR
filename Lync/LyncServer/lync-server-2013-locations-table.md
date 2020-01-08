---
title: 'Lync Server 2013: Locations 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b26f8c30c0d26fd265d95542b79f919153bc15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="2cc97-102">Lync Server 2013의 Locations 테이블</span><span class="sxs-lookup"><span data-stu-id="2cc97-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cc97-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="2cc97-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="2cc97-104">각 레코드는 E9-1-1 통화와 같이 비상 전화의 한 위치 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cc97-105">열</span><span class="sxs-lookup"><span data-stu-id="2cc97-105">Column</span></span></th>
<th><span data-ttu-id="2cc97-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2cc97-106">Data Type</span></span></th>
<th><span data-ttu-id="2cc97-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="2cc97-107">Key/Index</span></span></th>
<th><span data-ttu-id="2cc97-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="2cc97-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cc97-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2cc97-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc97-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="2cc97-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cc97-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="2cc97-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cc97-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-112">Time of session request.</span></span> <span data-ttu-id="2cc97-113">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cc97-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc97-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc97-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2cc97-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc97-116">int</span><span class="sxs-lookup"><span data-stu-id="2cc97-116">int</span></span></p></td>
<td><p><span data-ttu-id="2cc97-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="2cc97-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2cc97-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-118">ID number to identify the session.</span></span> <span data-ttu-id="2cc97-119">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2cc97-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc97-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc97-121"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="2cc97-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="2cc97-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2cc97-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2cc97-123">비상 전화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc97-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

