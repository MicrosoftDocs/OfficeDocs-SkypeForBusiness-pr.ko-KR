---
title: 'Lync Server 2013: ProgressReport view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="d58b8-102">Lync Server 2013의 ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="d58b8-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d58b8-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d58b8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d58b8-104">ProgressReport 보기는 완료 된 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="d58b8-105">진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="d58b8-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d58b8-107">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d58b8-108">열</span><span class="sxs-lookup"><span data-stu-id="d58b8-108">Column</span></span></th>
<th><span data-ttu-id="d58b8-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d58b8-109">Data Type</span></span></th>
<th><span data-ttu-id="d58b8-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="d58b8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d58b8-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="d58b8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d58b8-113">오류가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-113">Time of error occurred.</span></span> <span data-ttu-id="d58b8-114">오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d58b8-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-116">int</span><span class="sxs-lookup"><span data-stu-id="d58b8-116">int</span></span></p></td>
<td><p><span data-ttu-id="d58b8-117">오류를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-117">ID number to identify the error.</span></span> <span data-ttu-id="d58b8-118">오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d58b8-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-120">int</span><span class="sxs-lookup"><span data-stu-id="d58b8-120">int</span></span></p></td>
<td><p><span data-ttu-id="d58b8-121">진행률 보고서를 식별 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-121">ID to identify the progress report.</span></span> <span data-ttu-id="d58b8-122">같은 오류 보고서의 진행률 보고서를 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d58b8-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-124">int</span><span class="sxs-lookup"><span data-stu-id="d58b8-124">int</span></span></p></td>
<td><p><span data-ttu-id="d58b8-125">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d58b8-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d58b8-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d58b8-128">오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="d58b8-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d58b8-129"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d58b8-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d58b8-131">오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="d58b8-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d58b8-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d58b8-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d58b8-134">고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d58b8-135"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-136">int</span><span class="sxs-lookup"><span data-stu-id="d58b8-136">int</span></span></p></td>
<td><p><span data-ttu-id="d58b8-137">특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="d58b8-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d58b8-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="d58b8-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="d58b8-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="d58b8-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d58b8-140">추가 오류 정보.</span><span class="sxs-lookup"><span data-stu-id="d58b8-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

