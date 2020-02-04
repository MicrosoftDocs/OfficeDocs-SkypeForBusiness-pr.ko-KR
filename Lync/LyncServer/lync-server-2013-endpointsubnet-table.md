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
ms.openlocfilehash: 055aa9460fb63e96d20472d6102c249ecf71a78b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="d1417-102">Lync Server 2013의 EndpointSubnet 테이블</span><span class="sxs-lookup"><span data-stu-id="d1417-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1417-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d1417-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d1417-104">EndpointSubnet 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="d1417-104">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="d1417-105">각 레코드는 끝점에서 캡처된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1417-105">Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1417-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d1417-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d1417-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d1417-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1417-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="d1417-111">int</span><span class="sxs-lookup"><span data-stu-id="d1417-111">int</span></span></p></td>
<td><p><span data-ttu-id="d1417-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="d1417-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1417-113">서브넷에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="d1417-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1417-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d1417-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d1417-115">dmtf</span><span class="sxs-lookup"><span data-stu-id="d1417-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1417-116">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1417-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

