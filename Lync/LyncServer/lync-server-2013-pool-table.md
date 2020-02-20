---
title: 'Lync Server 2013: Pool 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e10e3e6a3e27d66510b4cde0ef72a1a11288e8e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="42d56-102">Lync Server 2013의 Pool 테이블</span><span class="sxs-lookup"><span data-stu-id="42d56-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d56-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="42d56-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="42d56-p101">Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42d56-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42d56-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="42d56-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="42d56-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="42d56-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42d56-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="42d56-111">int</span><span class="sxs-lookup"><span data-stu-id="42d56-111">int</span></span></p></td>
<td><p><span data-ttu-id="42d56-112">Primary</span><span class="sxs-lookup"><span data-stu-id="42d56-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="42d56-113">이 풀을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="42d56-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d56-114"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="42d56-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="42d56-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42d56-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42d56-116">고유한 </span><span class="sxs-lookup"><span data-stu-id="42d56-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="42d56-117">풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="42d56-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

