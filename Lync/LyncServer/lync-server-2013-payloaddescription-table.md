---
title: 'Lync Server 2013: PayloadDescription 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44edea16dc4874b797dd69402709a880c530147c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="70478-102">Lync Server 2013의 PayloadDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="70478-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70478-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="70478-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="70478-p101">PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 및 비디오 세션에 사용되는 하나의 코덱을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70478-p101">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70478-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="70478-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="70478-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="70478-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="70478-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="70478-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="70478-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="70478-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70478-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="70478-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="70478-111">int</span><span class="sxs-lookup"><span data-stu-id="70478-111">int</span></span></p></td>
<td><p><span data-ttu-id="70478-112">Primary</span><span class="sxs-lookup"><span data-stu-id="70478-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="70478-113">코덱을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="70478-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70478-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="70478-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="70478-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="70478-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70478-116">고유한</span><span class="sxs-lookup"><span data-stu-id="70478-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="70478-117">코덱 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70478-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

