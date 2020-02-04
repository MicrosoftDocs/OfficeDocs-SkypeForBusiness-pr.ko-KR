---
title: 'Lync Server 2013: Region 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Region table
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48183518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005722b28b6ea93d89873d45e7a9284f44643bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="region-table-in-lync-server-2013"></a><span data-ttu-id="21533-102">Lync Server 2013의 Region 테이블</span><span class="sxs-lookup"><span data-stu-id="21533-102">Region table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21533-103">_**마지막으로 수정한 주제:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="21533-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="21533-104">지역 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="21533-104">The Region table is a supporting table.</span></span> <span data-ttu-id="21533-105">각 레코드는 네트워크 구성 설정에 정의 된 하나의 국가/지역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21533-105">Each record represents one country/region defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21533-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="21533-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="21533-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="21533-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="21533-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="21533-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="21533-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="21533-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21533-110"><strong>국가 키</strong></span><span class="sxs-lookup"><span data-stu-id="21533-110"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="21533-111">int</span><span class="sxs-lookup"><span data-stu-id="21533-111">int</span></span></p></td>
<td><p><span data-ttu-id="21533-112">주요한</span><span class="sxs-lookup"><span data-stu-id="21533-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="21533-113">국가/지역을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="21533-113">Unique number identifying the country/region.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21533-114"><strong>국가 이름</strong></span><span class="sxs-lookup"><span data-stu-id="21533-114"><strong>RegionName</strong></span></span></p></td>
<td><p><span data-ttu-id="21533-115">name</span><span class="sxs-lookup"><span data-stu-id="21533-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="21533-116">독특한</span><span class="sxs-lookup"><span data-stu-id="21533-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="21533-117">국가/지역의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21533-117">The name of the country/region.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

