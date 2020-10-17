---
title: 'Lync Server 2013: 위치 테이블'
description: 'Lync Server 2013: 위치 테이블'
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
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570584"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="edfa0-103">Lync Server 2013의 위치 테이블</span><span class="sxs-lookup"><span data-stu-id="edfa0-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edfa0-104">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="edfa0-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="edfa0-105">각 레코드는 E9-1-1 통화와 같은 응급 통화에서 하나의 위치 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edfa0-106">열</span><span class="sxs-lookup"><span data-stu-id="edfa0-106">Column</span></span></th>
<th><span data-ttu-id="edfa0-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="edfa0-107">Data Type</span></span></th>
<th><span data-ttu-id="edfa0-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="edfa0-108">Key/Index</span></span></th>
<th><span data-ttu-id="edfa0-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="edfa0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edfa0-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="edfa0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="edfa0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="edfa0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="edfa0-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="edfa0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="edfa0-113">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-113">Time of session request.</span></span> <span data-ttu-id="edfa0-114"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="edfa0-115">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="edfa0-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edfa0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="edfa0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="edfa0-117">int</span><span class="sxs-lookup"><span data-stu-id="edfa0-117">int</span></span></p></td>
<td><p><span data-ttu-id="edfa0-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="edfa0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="edfa0-119">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-119">ID number to identify the session.</span></span> <span data-ttu-id="edfa0-120"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="edfa0-121">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="edfa0-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edfa0-122"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="edfa0-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="edfa0-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="edfa0-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edfa0-124">응급 통화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="edfa0-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

