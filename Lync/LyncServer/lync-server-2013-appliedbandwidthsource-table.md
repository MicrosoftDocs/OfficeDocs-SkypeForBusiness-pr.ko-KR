---
title: 'Lync Server 2013: AppliedBandwidthSource 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6978802893b2c4af4f4d4199c3e35452200d8d4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="9a613-102">Lync Server 2013의 AppliedBandwidthSource 테이블</span><span class="sxs-lookup"><span data-stu-id="9a613-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a613-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9a613-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9a613-104">AppliedBandwidthSource 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9a613-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="9a613-105">각 레코드는 하나의 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a613-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a613-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9a613-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9a613-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9a613-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a613-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9a613-111">int</span><span class="sxs-lookup"><span data-stu-id="9a613-111">int</span></span></p></td>
<td><p><span data-ttu-id="9a613-112">주요한</span><span class="sxs-lookup"><span data-stu-id="9a613-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9a613-113">출처를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9a613-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a613-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="9a613-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="9a613-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9a613-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9a613-116">독특한</span><span class="sxs-lookup"><span data-stu-id="9a613-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="9a613-117">적용 되는 대역폭 cap의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="9a613-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="9a613-118">대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").</span><span class="sxs-lookup"><span data-stu-id="9a613-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

