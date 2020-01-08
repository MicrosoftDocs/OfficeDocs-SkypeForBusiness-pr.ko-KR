---
title: 'Lync Server 2013: Gateways 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f26a45d992d716b94cb7353f813c038272b132
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="e4ce5-102">Lync Server 2013의 Gateways 테이블</span><span class="sxs-lookup"><span data-stu-id="e4ce5-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4ce5-103">_**마지막으로 수정한 주제:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="e4ce5-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="e4ce5-104">게이트웨이 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e4ce5-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="e4ce5-105">각 레코드는 데이터베이스에 레코드가 있는 PSTN (공개 교환 통신망) 통화와 관련 된 게이트웨이 하나에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ce5-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4ce5-106">열</span><span class="sxs-lookup"><span data-stu-id="e4ce5-106">Column</span></span></th>
<th><span data-ttu-id="e4ce5-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e4ce5-107">Data Type</span></span></th>
<th><span data-ttu-id="e4ce5-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="e4ce5-108">Key/Index</span></span></th>
<th><span data-ttu-id="e4ce5-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="e4ce5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4ce5-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="e4ce5-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="e4ce5-111">int</span><span class="sxs-lookup"><span data-stu-id="e4ce5-111">int</span></span></p></td>
<td><p><span data-ttu-id="e4ce5-112">주요한</span><span class="sxs-lookup"><span data-stu-id="e4ce5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4ce5-113">이 게이트웨이를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e4ce5-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4ce5-114"><strong>게이트웨이와</strong></span><span class="sxs-lookup"><span data-stu-id="e4ce5-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e4ce5-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4ce5-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e4ce5-116">게이트웨이 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4ce5-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

