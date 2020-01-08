---
title: 'Lync Server 2013: IPAddress 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82eef0e1926bc794df7c6a80b28fa68008561315
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="86010-102">Lync Server 2013의 IPAddress 테이블</span><span class="sxs-lookup"><span data-stu-id="86010-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86010-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="86010-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="86010-104">IPAddress 테이블은 경력 데이터베이스의 다른 곳에 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="86010-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="86010-105">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86010-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86010-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="86010-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="86010-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="86010-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="86010-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="86010-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="86010-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="86010-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86010-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="86010-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="86010-111">int</span><span class="sxs-lookup"><span data-stu-id="86010-111">int</span></span></p></td>
<td><p><span data-ttu-id="86010-112">주요한</span><span class="sxs-lookup"><span data-stu-id="86010-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="86010-113">지정 된 IP 주소에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="86010-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86010-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="86010-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="86010-115">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="86010-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="86010-116">독특한</span><span class="sxs-lookup"><span data-stu-id="86010-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="86010-117">IpAddressKey에 매핑되는 고유 IP 주소 (예: 189.168.1.1)입니다.</span><span class="sxs-lookup"><span data-stu-id="86010-117">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="86010-118">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86010-118">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

