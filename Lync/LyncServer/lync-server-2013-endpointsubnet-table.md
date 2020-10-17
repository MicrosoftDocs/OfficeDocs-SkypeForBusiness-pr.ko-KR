---
title: 'Lync Server 2013: EndpointSubnet 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b8414675109a69bec6baeceef4f4496bcf0c84
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533315"
---
# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="84d15-102">Lync Server 2013의 EndpointSubnet 테이블</span><span class="sxs-lookup"><span data-stu-id="84d15-102">EndpointSubnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84d15-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="84d15-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="84d15-p101">EndpointSubnet 테이블은 지원 테이블입니다. 각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84d15-p101">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84d15-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="84d15-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="84d15-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="84d15-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84d15-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="84d15-111">int</span><span class="sxs-lookup"><span data-stu-id="84d15-111">int</span></span></p></td>
<td><p><span data-ttu-id="84d15-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="84d15-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="84d15-113">정수로 표시된 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="84d15-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84d15-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="84d15-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="84d15-115">datetime</span><span class="sxs-lookup"><span data-stu-id="84d15-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84d15-116">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d15-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

