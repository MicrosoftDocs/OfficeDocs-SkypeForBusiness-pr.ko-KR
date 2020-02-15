---
title: 'Lync Server 2013: 회의 표'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733b3fc6fa77f8f18de1a5c79be86a5aea340cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="6721b-102">Lync Server 2013의 회의 테이블</span><span class="sxs-lookup"><span data-stu-id="6721b-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6721b-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6721b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6721b-p101">Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6721b-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6721b-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6721b-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6721b-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6721b-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6721b-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6721b-111">int</span><span class="sxs-lookup"><span data-stu-id="6721b-111">int</span></span></p></td>
<td><p><span data-ttu-id="6721b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6721b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6721b-113">이 회의 레코드를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6721b-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6721b-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="6721b-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6721b-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6721b-116">고유한</span><span class="sxs-lookup"><span data-stu-id="6721b-116">unique</span></span></p></td>
<td><p><span data-ttu-id="6721b-117">항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="6721b-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6721b-118"><strong>제외</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="6721b-119">int</span><span class="sxs-lookup"><span data-stu-id="6721b-119">int</span></span></p></td>
<td><p><span data-ttu-id="6721b-120">인덱스</span><span class="sxs-lookup"><span data-stu-id="6721b-120">index</span></span></p></td>
<td><p><span data-ttu-id="6721b-p102">회의 URI의 체크섬입니다. 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6721b-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6721b-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="6721b-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="6721b-124">datetime</span><span class="sxs-lookup"><span data-stu-id="6721b-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6721b-125">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6721b-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

