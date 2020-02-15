---
title: 'Lync Server 2013: Subnet 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff03309ab4c71f2dfda9aac96223cde2cd6e000a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="2de31-102">Lync Server 2013의 서브넷 테이블</span><span class="sxs-lookup"><span data-stu-id="2de31-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2de31-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2de31-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2de31-p101">Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2de31-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2de31-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2de31-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2de31-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2de31-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2de31-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="2de31-111">int</span><span class="sxs-lookup"><span data-stu-id="2de31-111">int</span></span></p></td>
<td><p><span data-ttu-id="2de31-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="2de31-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2de31-113">정수로 표시된 서브넷 IP입니다.</span><span class="sxs-lookup"><span data-stu-id="2de31-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de31-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="2de31-115">int</span><span class="sxs-lookup"><span data-stu-id="2de31-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2de31-116">서브넷 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="2de31-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de31-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2de31-118">int</span><span class="sxs-lookup"><span data-stu-id="2de31-118">int</span></span></p></td>
<td><p><span data-ttu-id="2de31-119">외부</span><span class="sxs-lookup"><span data-stu-id="2de31-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2de31-120"><a href="lync-server-2013-usersite-table.md">Lync Server 2013의 Usersite 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de31-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de31-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2de31-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2de31-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="2de31-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2de31-123">서브넷에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2de31-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

