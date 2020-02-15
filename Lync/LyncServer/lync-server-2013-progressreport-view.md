---
title: 'Lync Server 2013: ProgressReport 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="bff02-102">Lync Server 2013의 ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="bff02-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bff02-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="bff02-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="bff02-104">ProgressReport 보기에는 완료 된 세션에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="bff02-105">진행률 보고서는 Lync Server 2013에서 진단 목적에 따라 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="bff02-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bff02-107">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드가 반드시 오류를 참조할 필요는 없지만 통화 상태 또는 메시지를 나타내는 메시지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bff02-108">열</span><span class="sxs-lookup"><span data-stu-id="bff02-108">Column</span></span></th>
<th><span data-ttu-id="bff02-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bff02-109">Data Type</span></span></th>
<th><span data-ttu-id="bff02-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bff02-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bff02-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bff02-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="bff02-p102">오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff02-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-116">int</span><span class="sxs-lookup"><span data-stu-id="bff02-116">int</span></span></p></td>
<td><p><span data-ttu-id="bff02-p103">오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff02-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-120">int</span><span class="sxs-lookup"><span data-stu-id="bff02-120">int</span></span></p></td>
<td><p><span data-ttu-id="bff02-121">진행률 보고서를 식별 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-121">ID to identify the progress report.</span></span> <span data-ttu-id="bff02-122">동일한 오류 보고서의 진행 상황 보고서를 구별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff02-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-124">int</span><span class="sxs-lookup"><span data-stu-id="bff02-124">int</span></span></p></td>
<td><p><span data-ttu-id="bff02-125">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff02-126"><strong>원본</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bff02-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bff02-128">오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="bff02-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff02-129"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bff02-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bff02-131">오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="bff02-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff02-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-133">고유</span><span class="sxs-lookup"><span data-stu-id="bff02-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="bff02-134">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bff02-135"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-136">int</span><span class="sxs-lookup"><span data-stu-id="bff02-136">int</span></span></p></td>
<td><p><span data-ttu-id="bff02-137">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bff02-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="bff02-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="bff02-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="bff02-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="bff02-140">추가 오류 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="bff02-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

