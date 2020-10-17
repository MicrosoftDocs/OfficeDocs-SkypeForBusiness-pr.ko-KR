---
title: 'Lync Server 2013: IMReportSummary 테이블'
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
ms.openlocfilehash: 5e750da3fd42a726012f089291d3e2c770e52b44
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526635"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="fddca-102">Lync Server 2013의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="fddca-102">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fddca-103">_**마지막으로 수정 된 항목:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="fddca-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="fddca-104">IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="fddca-105">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fddca-106">열</span><span class="sxs-lookup"><span data-stu-id="fddca-106">Column</span></span></th>
<th><span data-ttu-id="fddca-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fddca-107">Data Type</span></span></th>
<th><span data-ttu-id="fddca-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="fddca-108">Key/Index</span></span></th>
<th><span data-ttu-id="fddca-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fddca-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fddca-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fddca-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fddca-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fddca-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fddca-113">인스턴트 메시징 세션이 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fddca-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="fddca-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="fddca-116">Primary</span><span class="sxs-lookup"><span data-stu-id="fddca-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fddca-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="fddca-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="fddca-119">Primary</span><span class="sxs-lookup"><span data-stu-id="fddca-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="fddca-120">세션을 호스팅하는 풀의 정규화된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fddca-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-122">int</span><span class="sxs-lookup"><span data-stu-id="fddca-122">int</span></span></p></td>
<td><p><span data-ttu-id="fddca-123">Primary</span><span class="sxs-lookup"><span data-stu-id="fddca-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="fddca-124">통화의 우선 순위(예: 긴급, 일반)입니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="fddca-125">우선 순위 정보는 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 callpriorities 테이블</a>에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fddca-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-127">bigint</span><span class="sxs-lookup"><span data-stu-id="fddca-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fddca-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="fddca-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fddca-129">bigint</span><span class="sxs-lookup"><span data-stu-id="fddca-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fddca-130">세션 중 교환된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fddca-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

