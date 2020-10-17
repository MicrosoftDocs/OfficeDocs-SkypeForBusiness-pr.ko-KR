---
title: 'Lync Server 2013: IMReportSummary 테이블'
description: 'Lync Server 2013: IMReportSummary 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547744"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="72c57-103">Lync Server 2013의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="72c57-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72c57-104">_**마지막으로 수정 된 항목:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="72c57-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="72c57-105">IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="72c57-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72c57-107">열</span><span class="sxs-lookup"><span data-stu-id="72c57-107">Column</span></span></th>
<th><span data-ttu-id="72c57-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="72c57-108">Data Type</span></span></th>
<th><span data-ttu-id="72c57-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="72c57-109">Key/Index</span></span></th>
<th><span data-ttu-id="72c57-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="72c57-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72c57-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-112">datetime</span><span class="sxs-lookup"><span data-stu-id="72c57-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="72c57-113">Primary</span><span class="sxs-lookup"><span data-stu-id="72c57-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="72c57-114">인스턴트 메시징 세션이 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72c57-115"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="72c57-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="72c57-117">Primary</span><span class="sxs-lookup"><span data-stu-id="72c57-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72c57-118"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="72c57-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="72c57-120">Primary</span><span class="sxs-lookup"><span data-stu-id="72c57-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="72c57-121">세션을 호스팅하는 풀의 정규화된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72c57-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-123">int</span><span class="sxs-lookup"><span data-stu-id="72c57-123">int</span></span></p></td>
<td><p><span data-ttu-id="72c57-124">Primary</span><span class="sxs-lookup"><span data-stu-id="72c57-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="72c57-125">통화의 우선 순위(예: 긴급, 일반)입니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="72c57-126">우선 순위 정보는 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 callpriorities 테이블</a>에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72c57-127"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-128">bigint</span><span class="sxs-lookup"><span data-stu-id="72c57-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72c57-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="72c57-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="72c57-130">bigint</span><span class="sxs-lookup"><span data-stu-id="72c57-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72c57-131">세션 중 교환된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="72c57-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

