---
title: 'Lync Server 2013: IPAddress 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d23e9aba844cb03779b220ed8d898a2e7664891
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514175"
---
# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="a7059-102">Lync Server 2013의 IPAddress 테이블</span><span class="sxs-lookup"><span data-stu-id="a7059-102">IPAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7059-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a7059-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a7059-104">IPAddress 테이블은 QoE(체감 품질) 데이터베이스의 모든 위치에서 사용되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a7059-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a7059-105">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7059-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7059-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a7059-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a7059-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a7059-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7059-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a7059-111">int</span><span class="sxs-lookup"><span data-stu-id="a7059-111">int</span></span></p></td>
<td><p><span data-ttu-id="a7059-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a7059-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a7059-113">지정된 IP 주소의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7059-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7059-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a7059-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a7059-115">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7059-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="a7059-116">고유한</span><span class="sxs-lookup"><span data-stu-id="a7059-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a7059-p102">IpAddressKey에 매핑되는 고유 IP 주소(예: 189.168.1.1)입니다. IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7059-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

