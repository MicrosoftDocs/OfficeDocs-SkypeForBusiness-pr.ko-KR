---
title: 결과 해석
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="020ee-102">결과 해석</span><span class="sxs-lookup"><span data-stu-id="020ee-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="020ee-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="020ee-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="020ee-104">Lync Server 2013 스트레스 및 성능 도구 (L Cperftool. exe)에는 클라이언트가 수행 하는 작업과 문제가 발생 하는지 여부를 이해 하는 데 사용할 수 있는 많은 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="020ee-105">클라이언트 카운터</span><span class="sxs-lookup"><span data-stu-id="020ee-105">Client Counters</span></span>

<span data-ttu-id="020ee-106">실행 중인 L이라는 Cperftool의 각 인스턴스에는 별도의 카운터 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="020ee-107">각 인스턴스는 해당 프로세스 ID로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="020ee-108">클라이언트가 오버 로드 되 면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="020ee-109">이러한 문제를 방지 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="020ee-110">클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="020ee-111">CPU가 90 퍼센트 이상으로 일관 되는 경우 사용자 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="020ee-112">메모리 공간이 높으면 페이지 파일의 크기가 충분 하지 않은 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="020ee-113">커밋 충전량이 컴퓨터의 한도에 도달 하 고 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="020ee-114">메모리 제한을 실행 하는 경우 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="020ee-115">다음 표에는 key L Cperftool 성능 카운터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="020ee-116">**일반 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-117"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-118"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-119">분 내에 소요 된 시간</span><span class="sxs-lookup"><span data-stu-id="020ee-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="020ee-120">프로세스가 시작 된 이후 경과한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-121">활성 끝점</span><span class="sxs-lookup"><span data-stu-id="020ee-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="020ee-122">현재 서버에 연결 된 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-123">실패 한 로그온</span><span class="sxs-lookup"><span data-stu-id="020ee-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="020ee-124">끝점 로그인 실패의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-125">로그온 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="020ee-126">끝점 로그인 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-127">끝점 연결 끊김</span><span class="sxs-lookup"><span data-stu-id="020ee-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="020ee-128">연결이 끊어진 끝점의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-129">**현재 상태 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-130"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-131"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-132">SetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="020ee-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="020ee-133">현재 상태 변경 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-133">Total number of presence change attempts.</span></span> <span data-ttu-id="020ee-134">다른 유형의 현재 변경 내용에 대해서는 SetPresence 상태 (현재 상태 유형) 통화 성능 카운터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="020ee-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-135">NNN의 SetPresence 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="020ee-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="020ee-136">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-137">GetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="020ee-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="020ee-138">현재 상태 요청 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-139">A GetPresence 상태에 대 한 NNN 응답</span><span class="sxs-lookup"><span data-stu-id="020ee-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="020ee-140">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-141">**주소록 서비스 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-141">**Address Book service Information**</span></span>

<span data-ttu-id="020ee-142">이 범주에는 ABS (주소록 서비스) 파일 다운로드 및 주소록 웹 쿼리 서비스 요청을 모니터링 하는 데 사용 되는 카운터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-143"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-144"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-145">ABS 전체/델타 파일 다운로드를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-146">시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-147">ABS 전체/델타 파일 다운로드 성공</span><span class="sxs-lookup"><span data-stu-id="020ee-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="020ee-148">시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-149">주소록 웹 쿼리 서비스 관련 카운터</span><span class="sxs-lookup"><span data-stu-id="020ee-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="020ee-150">주소록 파일 다운로드 관련 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-151">ABS WS 호출 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-152">시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-153">ABS WS 호출 성공</span><span class="sxs-lookup"><span data-stu-id="020ee-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="020ee-154">성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-155">ABS WS 호출 실패</span><span class="sxs-lookup"><span data-stu-id="020ee-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="020ee-156">오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-157">**DL (메일 그룹) 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-158"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-159"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-160">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="020ee-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-161">시도 된 DLX (메일 그룹 확장) 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-162">통화 성공</span><span class="sxs-lookup"><span data-stu-id="020ee-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="020ee-163">성공적인 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-164">통화 실패</span><span class="sxs-lookup"><span data-stu-id="020ee-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="020ee-165">오류 응답 코드를 반환 하는 DLX 웹 서비스 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-166">**VoIP 기본 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="020ee-167">다음 시나리오를 사용 하는 경우 중재 서버, A/V 회의 서버, Edge 서버, 응답 그룹 응용 프로그램, 회의 자동 전화 교환 등의 호출을 포함 하 여 모든 VoIP (Voice over IP) 통화에 대 한 번호를 아래에 나열 된 성능 카운터를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-168"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-169"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-170">통화 활성</span><span class="sxs-lookup"><span data-stu-id="020ee-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="020ee-171">현재 진행 중인 총 수신/발신 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-172">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="020ee-173">이미 종료 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-174">통화가 거절 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="020ee-175">거절 된 총 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-176">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-177">시도한 총 수신/발신 음성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-178">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="020ee-179">설정 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-180">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="020ee-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="020ee-181">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-182">VoIP 통과 율 (%)</span><span class="sxs-lookup"><span data-stu-id="020ee-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="020ee-183">총 통화/총 통화를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-184">**응답 그룹 서비스 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-185"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-186"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-187">통화 활성</span><span class="sxs-lookup"><span data-stu-id="020ee-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="020ee-188">응답 그룹 응용 프로그램에 대 한 총 활성 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-189">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="020ee-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-190">시도한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-191">**인스턴트 메시지 (IM) 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-192"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-193"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-194">통화 활성</span><span class="sxs-lookup"><span data-stu-id="020ee-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="020ee-195">진행 중인 수신/발신 인스턴트 메시징 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-196">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="020ee-197">이미 종료 된 수신/발신 인스턴트 메시징 전화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-198">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="020ee-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="020ee-199">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-200">수신/전송 된 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="020ee-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="020ee-201">모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-202">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-203">시도한 총 수신/발신 인스턴트 메시징 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-204">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="020ee-205">설정 된 수신/발신 인스턴트 메시지 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-206">**앱 공유 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-207"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-208"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-209">통화 활성</span><span class="sxs-lookup"><span data-stu-id="020ee-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="020ee-210">진행 중인 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-211">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="020ee-212">이미 종료 된 수신/발신 응용 프로그램 공유 전화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-213">받은 통화 NNN</span><span class="sxs-lookup"><span data-stu-id="020ee-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="020ee-214">서버에서 받은 총 nnn response 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-215">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-216">시도한 총 수신/발신 응용 프로그램 공유 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-217">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="020ee-218">설정 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-219">**통화 정보를 ca**</span><span class="sxs-lookup"><span data-stu-id="020ee-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-220"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-221"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-222">통화 활성</span><span class="sxs-lookup"><span data-stu-id="020ee-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="020ee-223">현재 진행 중인 수신/송신 공공 전화망 (PSTN) 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-224">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="020ee-225">이미 종료 된 수신/송신 PSTN 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-226">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="020ee-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="020ee-227">시도한 총 수신/송신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-228">수신/발신 통화가 설정 됨</span><span class="sxs-lookup"><span data-stu-id="020ee-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="020ee-229">설정 된 수신/발신 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-230">**컨퍼런스 정보**</span><span class="sxs-lookup"><span data-stu-id="020ee-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-231"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-232"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-233">활성 인스턴트 메시지 회의</span><span class="sxs-lookup"><span data-stu-id="020ee-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="020ee-234">진행 중인 인스턴트 메시지 회의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-235">활성 오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="020ee-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="020ee-236">진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-237">활성 응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="020ee-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="020ee-238">진행 중인 응용 프로그램 공유 컨퍼런스의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-239">참가자 수</span><span class="sxs-lookup"><span data-stu-id="020ee-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="020ee-240">현재 컨퍼런스에 연결 된 총 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020ee-241">컨퍼런스 일정 실패</span><span class="sxs-lookup"><span data-stu-id="020ee-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="020ee-242">회의를 예약 하려고 시도 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-243">컨퍼런스 참가 실패</span><span class="sxs-lookup"><span data-stu-id="020ee-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="020ee-244">회의에 연결 하려고 시도 하는 동안 발생 한 총 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="020ee-245">**A/WA 클라이언트 카운터**</span><span class="sxs-lookup"><span data-stu-id="020ee-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020ee-246"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="020ee-247"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="020ee-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020ee-248">성공한 IMMCU 조인의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="020ee-249">참가 한 총 인스턴트 메시징 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020ee-250">성공한 DMCU 조인의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="020ee-251">참가 한 총 A/V 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="020ee-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

