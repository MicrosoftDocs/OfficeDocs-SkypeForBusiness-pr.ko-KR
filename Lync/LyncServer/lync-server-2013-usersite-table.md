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
ms.openlocfilehash: 7e316fe33ac77784a681a71b9cabd0613bb1cc1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="82af2-102">Lync Server 2013의 UserSite 테이블</span><span class="sxs-lookup"><span data-stu-id="82af2-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82af2-103">_**마지막으로 수정한 주제:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="82af2-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="82af2-104">UserSite 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="82af2-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="82af2-105">각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82af2-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82af2-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="82af2-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="82af2-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="82af2-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82af2-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="82af2-111">int</span><span class="sxs-lookup"><span data-stu-id="82af2-111">int</span></span></p></td>
<td><p><span data-ttu-id="82af2-112">주요한</span><span class="sxs-lookup"><span data-stu-id="82af2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="82af2-113">사용자 사이트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="82af2-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82af2-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="82af2-115">name</span><span class="sxs-lookup"><span data-stu-id="82af2-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="82af2-116">독특한</span><span class="sxs-lookup"><span data-stu-id="82af2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="82af2-117">사용자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82af2-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82af2-118"><strong>국가 키</strong></span><span class="sxs-lookup"><span data-stu-id="82af2-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="82af2-119">int</span><span class="sxs-lookup"><span data-stu-id="82af2-119">int</span></span></p></td>
<td><p><span data-ttu-id="82af2-120">외부</span><span class="sxs-lookup"><span data-stu-id="82af2-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82af2-121"><a href="lync-server-2013-region-table.md">Lync Server 2013의 지역 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="82af2-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

