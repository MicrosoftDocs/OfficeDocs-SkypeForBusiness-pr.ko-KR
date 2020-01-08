---
title: 'Lync Server 2013: Subnet 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="ec60f-102">Lync Server 2013의 Subnet 테이블</span><span class="sxs-lookup"><span data-stu-id="ec60f-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec60f-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ec60f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ec60f-104">서브넷 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ec60f-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="ec60f-105">각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec60f-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec60f-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ec60f-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ec60f-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ec60f-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec60f-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="ec60f-111">int</span><span class="sxs-lookup"><span data-stu-id="ec60f-111">int</span></span></p></td>
<td><p><span data-ttu-id="ec60f-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="ec60f-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec60f-113">서브넷 IP에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="ec60f-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec60f-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="ec60f-115">int</span><span class="sxs-lookup"><span data-stu-id="ec60f-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec60f-116">서브넷 마스크.</span><span class="sxs-lookup"><span data-stu-id="ec60f-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec60f-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ec60f-118">int</span><span class="sxs-lookup"><span data-stu-id="ec60f-118">int</span></span></p></td>
<td><p><span data-ttu-id="ec60f-119">외부</span><span class="sxs-lookup"><span data-stu-id="ec60f-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ec60f-120"><a href="lync-server-2013-usersite-table.md">Lync Server 2013의 Usersite 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec60f-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec60f-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ec60f-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ec60f-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="ec60f-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec60f-123">서브넷에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ec60f-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

