---
title: 'Lync Server 2013: IMReportSummary 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="4c542-102">Lync Server 2013의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="4c542-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c542-103">_**마지막으로 수정한 주제:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="4c542-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="4c542-104">Imreport요약 테이블은 조직에 보관 된 인스턴트 메시징 세션에 대 한 전반적인 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="4c542-105">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c542-106">열</span><span class="sxs-lookup"><span data-stu-id="4c542-106">Column</span></span></th>
<th><span data-ttu-id="4c542-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4c542-107">Data Type</span></span></th>
<th><span data-ttu-id="4c542-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="4c542-108">Key/Index</span></span></th>
<th><span data-ttu-id="4c542-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="4c542-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c542-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="4c542-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c542-112">주요한</span><span class="sxs-lookup"><span data-stu-id="4c542-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c542-113">인스턴트 메시징 세션이 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c542-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="4c542-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="4c542-116">주요한</span><span class="sxs-lookup"><span data-stu-id="4c542-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c542-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="4c542-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="4c542-119">주요한</span><span class="sxs-lookup"><span data-stu-id="4c542-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c542-120">세션을 호스트 하는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c542-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-122">int</span><span class="sxs-lookup"><span data-stu-id="4c542-122">int</span></span></p></td>
<td><p><span data-ttu-id="4c542-123">주요한</span><span class="sxs-lookup"><span data-stu-id="4c542-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c542-124">우선 순위 (예: 긴급 또는 비 긴급 통화)</span><span class="sxs-lookup"><span data-stu-id="4c542-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="4c542-125">우선 순위 정보는 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 callpriorities 테이블</a>에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c542-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-127">bigint</span><span class="sxs-lookup"><span data-stu-id="4c542-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c542-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="4c542-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4c542-129">bigint</span><span class="sxs-lookup"><span data-stu-id="4c542-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c542-130">세션 중에 교환 된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c542-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

