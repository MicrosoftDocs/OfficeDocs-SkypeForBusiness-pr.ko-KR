---
title: 'Lync Server 2013: UserSite 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d416017afdc36eefaffd3269359bcd0192a0c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="1c233-102">Lync Server 2013의 UserSite 테이블</span><span class="sxs-lookup"><span data-stu-id="1c233-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c233-103">_**마지막으로 수정 된 항목:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="1c233-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="1c233-p101">UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c233-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c233-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1c233-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1c233-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1c233-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c233-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1c233-111">int</span><span class="sxs-lookup"><span data-stu-id="1c233-111">int</span></span></p></td>
<td><p><span data-ttu-id="1c233-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1c233-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1c233-113">사용자 사이트를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1c233-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c233-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="1c233-115">name</span><span class="sxs-lookup"><span data-stu-id="1c233-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1c233-116">고유한</span><span class="sxs-lookup"><span data-stu-id="1c233-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="1c233-117">사용자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c233-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c233-118"><strong>지역 키</strong></span><span class="sxs-lookup"><span data-stu-id="1c233-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1c233-119">int</span><span class="sxs-lookup"><span data-stu-id="1c233-119">int</span></span></p></td>
<td><p><span data-ttu-id="1c233-120">외부</span><span class="sxs-lookup"><span data-stu-id="1c233-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1c233-121"><a href="lync-server-2013-region-table.md">Lync Server 2013의 Region from table</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c233-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

