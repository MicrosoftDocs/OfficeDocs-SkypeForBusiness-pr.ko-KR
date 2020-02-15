---
title: 'Lync Server 2013: ProgressReport 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aae907981e04d8966bb7eac4229232056d1004e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="00ecf-102">Lync Server 2013의 ProgressReport 테이블</span><span class="sxs-lookup"><span data-stu-id="00ecf-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00ecf-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="00ecf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="00ecf-104">진행률 보고서는 통화 또는 세션이 완료된 후에 클라이언트가 데이터베이스에 업로드한 데이터를 기반으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="00ecf-105">진행률 보고서는 Lync Server 2013에서 진단 목적에 따라 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="00ecf-106">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드가 반드시 오류를 참조할 필요는 없지만 통화 상태 또는 메시지를 나타내는 메시지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00ecf-107">열</span><span class="sxs-lookup"><span data-stu-id="00ecf-107">Column</span></span></th>
<th><span data-ttu-id="00ecf-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="00ecf-108">Data Type</span></span></th>
<th><span data-ttu-id="00ecf-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="00ecf-109">Key/Index</span></span></th>
<th><span data-ttu-id="00ecf-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="00ecf-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00ecf-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-112">datetime</span><span class="sxs-lookup"><span data-stu-id="00ecf-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="00ecf-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="00ecf-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00ecf-114">이 진행률 보고서를 포함하는 진행 상태 오류 보고서의 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="00ecf-115">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00ecf-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00ecf-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-117">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-117">int</span></span></p></td>
<td><p><span data-ttu-id="00ecf-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="00ecf-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00ecf-119">ErrorTime, ProgressReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용된 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="00ecf-120">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00ecf-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00ecf-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-122">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-122">int</span></span></p></td>
<td><p><span data-ttu-id="00ecf-123">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="00ecf-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="00ecf-124">오류 보고서를 식별하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-124">ID number that identifies the error report.</span></span> <span data-ttu-id="00ecf-125">ErrorReporSeq는 ErrorTime과 함께 오류 보고서를 고유하게 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="00ecf-126">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="00ecf-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="00ecf-127">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00ecf-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-129">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-129">int</span></span></p></td>
<td><p><span data-ttu-id="00ecf-130">Primary</span><span class="sxs-lookup"><span data-stu-id="00ecf-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="00ecf-p105">진행률 보고서를 식별하기 위한 ID 번호입니다. ErrorTime 및 ErrorReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00ecf-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-134">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00ecf-135">진행률 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="00ecf-136">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00ecf-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-138">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-138">int</span></span></p></td>
<td><p><span data-ttu-id="00ecf-139">외부</span><span class="sxs-lookup"><span data-stu-id="00ecf-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="00ecf-140">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 된 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="00ecf-141">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오. 이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00ecf-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-143">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00ecf-p107">보고서의 대상 Lync Server 프로세스입니다. 자세한 내용은 Application 테이블을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00ecf-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00ecf-146"><strong>사항은</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-147">이미지나</span><span class="sxs-lookup"><span data-stu-id="00ecf-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00ecf-148">공간 절약을 위해 이진 형식으로 저장된 진행률 보고서 세부 정보입니다. 다음 구문을 사용하여 이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="00ecf-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="00ecf-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00ecf-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-151">고유</span><span class="sxs-lookup"><span data-stu-id="00ecf-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00ecf-152">전화 회의에 참가하는 각 구성 요소의 참가 시간 정보에 대해 상관 관계를 지정하는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="00ecf-153">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00ecf-154"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="00ecf-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="00ecf-155">int</span><span class="sxs-lookup"><span data-stu-id="00ecf-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="00ecf-156">특정 구성 요소가 전화 회의에 참가하는 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="00ecf-157">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ecf-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

