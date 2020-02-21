---
title: 'Lync Server 2013: NetworkConnectionDetail 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58935c4043246a0c5a6c5d4d9cde19ca27627dcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="c7e2f-102">Lync Server 2013의 NetworkConnectionDetail 테이블</span><span class="sxs-lookup"><span data-stu-id="c7e2f-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7e2f-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c7e2f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c7e2f-104">NetworkConnectionDetail 테이블은 네트워크 연결 유형을 체감 품질 데이터베이스의 다른 위치에서 사용 되는 네트워크 연결 식별자에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="c7e2f-105">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7e2f-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c7e2f-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c7e2f-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c7e2f-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7e2f-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e2f-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c7e2f-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c7e2f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c7e2f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7e2f-113">네트워크 연결 유형의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7e2f-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="c7e2f-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e2f-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7e2f-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7e2f-116">고유한</span><span class="sxs-lookup"><span data-stu-id="c7e2f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="c7e2f-117">NetworkConnectionDetailKey에 해당 하는 네트워크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="c7e2f-118">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="c7e2f-119">0--유선</span><span class="sxs-lookup"><span data-stu-id="c7e2f-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="c7e2f-120">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="c7e2f-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="c7e2f-121">2--이더넷</span><span class="sxs-lookup"><span data-stu-id="c7e2f-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

