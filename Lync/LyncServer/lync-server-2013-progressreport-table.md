---
title: 'Lync Server 2013: ProgressReport 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="7b906-102">Lync Server 2013의 ProgressReport 테이블</span><span class="sxs-lookup"><span data-stu-id="7b906-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b906-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7b906-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7b906-104">진행률 보고서는 호출 또는 세션이 완료 된 후 클라이언트에서 데이터베이스에 업로드 한 데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="7b906-105">진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="7b906-106">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b906-107">열</span><span class="sxs-lookup"><span data-stu-id="7b906-107">Column</span></span></th>
<th><span data-ttu-id="7b906-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7b906-108">Data Type</span></span></th>
<th><span data-ttu-id="7b906-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="7b906-109">Key/Index</span></span></th>
<th><span data-ttu-id="7b906-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="7b906-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b906-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="7b906-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7b906-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7b906-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b906-114">이 진행률 보고서가 포함 된 진행률 오류 보고서의 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="7b906-115">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b906-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b906-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-117">int</span><span class="sxs-lookup"><span data-stu-id="7b906-117">int</span></span></p></td>
<td><p><span data-ttu-id="7b906-118">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7b906-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b906-119">상태 보고서를 고유 하 게 식별 하는 ProgressReportSeq ErrorTime과 함께 사용 되는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="7b906-120">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b906-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b906-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-122">int</span><span class="sxs-lookup"><span data-stu-id="7b906-122">int</span></span></p></td>
<td><p><span data-ttu-id="7b906-123">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7b906-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b906-124">오류 보고서를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-124">ID number that identifies the error report.</span></span> <span data-ttu-id="7b906-125">ErrorReporSeq는 오류 보고서를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="7b906-126">자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b906-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="7b906-127">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b906-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-129">int</span><span class="sxs-lookup"><span data-stu-id="7b906-129">int</span></span></p></td>
<td><p><span data-ttu-id="7b906-130">주요한</span><span class="sxs-lookup"><span data-stu-id="7b906-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b906-131">진행률 보고서를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-131">ID number to identify the progress report.</span></span> <span data-ttu-id="7b906-132">진행률 보고서를 고유 하 게 식별 하는 ErrorTime 및 Errortime Seq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b906-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-134">int</span><span class="sxs-lookup"><span data-stu-id="7b906-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b906-135">진행률 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="7b906-136">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b906-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-138">int</span><span class="sxs-lookup"><span data-stu-id="7b906-138">int</span></span></p></td>
<td><p><span data-ttu-id="7b906-139">외부</span><span class="sxs-lookup"><span data-stu-id="7b906-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b906-140">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 된 경우)</span><span class="sxs-lookup"><span data-stu-id="7b906-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="7b906-141">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요. 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b906-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-143">int</span><span class="sxs-lookup"><span data-stu-id="7b906-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b906-144">보고서에 대 한 Lync Server 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="7b906-145">자세한 내용은 응용 프로그램 테이블을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b906-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b906-146"><strong>도</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-147">이미지</span><span class="sxs-lookup"><span data-stu-id="7b906-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b906-148">공간 절약을 위해 이진 형식으로 저장 된 진행률 보고서 세부 정보입니다. 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="7b906-149">cast (cast (varbinary (max)로 Detail)를 varchar (max)로 캐스트)</span><span class="sxs-lookup"><span data-stu-id="7b906-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b906-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="7b906-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b906-152">컨퍼런스와 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연관 시키는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="7b906-153">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b906-154"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="7b906-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7b906-155">int</span><span class="sxs-lookup"><span data-stu-id="7b906-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b906-156">특정 구성 요소가 컨퍼런스에 참가 하는 데 걸리는 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="7b906-157">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b906-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

