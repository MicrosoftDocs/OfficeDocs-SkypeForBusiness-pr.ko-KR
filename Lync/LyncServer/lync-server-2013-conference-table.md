---
title: 'Lync Server 2013: Conference 테이블'
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
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="3bb63-102">Lync Server 2013의 Conference 테이블</span><span class="sxs-lookup"><span data-stu-id="3bb63-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bb63-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3bb63-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3bb63-104">회의 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="3bb63-105">각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bb63-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3bb63-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3bb63-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3bb63-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bb63-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3bb63-111">int</span><span class="sxs-lookup"><span data-stu-id="3bb63-111">int</span></span></p></td>
<td><p><span data-ttu-id="3bb63-112">주요한</span><span class="sxs-lookup"><span data-stu-id="3bb63-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3bb63-113">이 회의 레코드를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bb63-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="3bb63-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3bb63-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3bb63-116">독특한</span><span class="sxs-lookup"><span data-stu-id="3bb63-116">unique</span></span></p></td>
<td><p><span data-ttu-id="3bb63-117">회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bb63-118"><strong>검사</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="3bb63-119">int</span><span class="sxs-lookup"><span data-stu-id="3bb63-119">int</span></span></p></td>
<td><p><span data-ttu-id="3bb63-120">색인</span><span class="sxs-lookup"><span data-stu-id="3bb63-120">index</span></span></p></td>
<td><p><span data-ttu-id="3bb63-121">회의 URI의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-121">Checksum of the conference URI.</span></span> <span data-ttu-id="3bb63-122">이는 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bb63-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3bb63-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3bb63-124">dmtf</span><span class="sxs-lookup"><span data-stu-id="3bb63-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3bb63-125">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb63-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

