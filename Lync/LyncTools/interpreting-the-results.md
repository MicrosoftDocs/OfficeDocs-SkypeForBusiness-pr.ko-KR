---
title: 결과 해석
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="d6885-102">결과 해석</span><span class="sxs-lookup"><span data-stu-id="d6885-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6885-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d6885-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d6885-104">Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool.exe)에는 클라이언트가 수행 하는 작업과 문제가 발생 하는지 여부를 이해 하는 데 사용할 수 있는 많은 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="d6885-105">클라이언트 카운터</span><span class="sxs-lookup"><span data-stu-id="d6885-105">Client Counters</span></span>

<span data-ttu-id="d6885-106">실행 중인 각 LyncPerfTool.exe 인스턴스에는 별도의 카운터 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="d6885-107">각 인스턴스의 이름은 해당 프로세스 ID에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="d6885-108">클라이언트가 오버 로드 되 면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="d6885-109">이러한 문제를 방지 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="d6885-110">클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="d6885-111">CPU가 지속적으로 90% 이상 지속 되 면 사용자 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="d6885-112">메모리 공간이 높으면 페이지 파일 크기가 충분 하지 않은 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="d6885-113">컴퓨터에서 커밋 충전량이 한도를 적중 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="d6885-114">메모리 제한으로 실행 하는 경우에는 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="d6885-115">다음 표에서는 키 LyncPerfTool 성능 카운터를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="d6885-116">**일반 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-117"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-118"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-119">소요 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d6885-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="d6885-120">프로세스를 시작한 후 소요 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-121">활성 끝점</span><span class="sxs-lookup"><span data-stu-id="d6885-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="d6885-122">현재 서버에 연결 되어 있는 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-123">실패 한 로그온</span><span class="sxs-lookup"><span data-stu-id="d6885-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="d6885-124">끝점 로그인 실패의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-125">로그온 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="d6885-126">끝점 로그인 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-127">끝점 연결 끊기</span><span class="sxs-lookup"><span data-stu-id="d6885-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="d6885-128">연결을 끊은 총 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-129">**현재 상태 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-130"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-131"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-132">SetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="d6885-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="d6885-133">현재 상태 변경 시도 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-133">Total number of presence change attempts.</span></span> <span data-ttu-id="d6885-134">다른 유형의 현재 변경 내용은 SetPresence 상태 (현재 유형) 통화 성능 카운터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6885-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-135">NNN 현재 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="d6885-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="d6885-136">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-137">GetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="d6885-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="d6885-138">현재 상태 요청 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-139">NNN-GetPresence 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="d6885-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="d6885-140">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-141">**주소록 서비스 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-141">**Address Book service Information**</span></span>

<span data-ttu-id="d6885-142">이 범주에는 ABS (주소록 서비스) 파일 다운로드 및 주소록 웹 쿼리 서비스 요청을 모니터링 하는 데 사용 되는 카운터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-143"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-144"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-145">ABS 전체/델타 파일 다운로드 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-146">시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-147">ABS 전체/델타 파일 다운로드 성공</span><span class="sxs-lookup"><span data-stu-id="d6885-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6885-148">시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-149">주소록 웹 쿼리 서비스 관련 카운터</span><span class="sxs-lookup"><span data-stu-id="d6885-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="d6885-150">주소록 파일 다운로드 관련 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-151">ABS WS 호출이 시도 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-152">시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-153">ABS WS 호출이 성공 함</span><span class="sxs-lookup"><span data-stu-id="d6885-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6885-154">성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-155">ABS WS 호출이 실패 함</span><span class="sxs-lookup"><span data-stu-id="d6885-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="d6885-156">오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-157">**메일 그룹 (DL) 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-158"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-159"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-160">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="d6885-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-161">시도 된 DLX (총 메일 그룹 확장) 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-162">통화 성공</span><span class="sxs-lookup"><span data-stu-id="d6885-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6885-163">성공적인 응답 코드를 반환한 총 DLX web service 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-164">통화 실패</span><span class="sxs-lookup"><span data-stu-id="d6885-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="d6885-165">오류 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-166">**VoIP 기본 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="d6885-167">이 시나리오를 사용 하도록 설정 하는 경우 중재 서버, A/V 회의 서버,에 지 서버, 응답 그룹 응용 프로그램 및 전화 회의 자동 전화 교환에 대 한 호출을 비롯 하 여 모든 VoIP (Voice over IP) 통화에 대 한 보고서 번호 아래에 나열 된 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="d6885-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-168"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-169"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-170">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6885-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6885-171">현재 진행 중인 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-172">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6885-173">이미 종료 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-174">통화가 거절 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="d6885-175">거절 된 들어오는 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-176">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-177">시도 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-178">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6885-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6885-179">설정 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-180">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6885-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6885-181">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-182">VoIP 통과 속도 (%)</span><span class="sxs-lookup"><span data-stu-id="d6885-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="d6885-183">총 통화 횟수 설정/총 통화를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-184">**응답 그룹 서비스 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-185"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-186"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-187">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6885-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6885-188">응답 그룹 응용 프로그램에 대 한 총 활성 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-189">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="d6885-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-190">시도한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-191">**IM (인스턴트 메시징) 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-192"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-193"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-194">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6885-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6885-195">진행 된 수신/발신 인스턴트 메시징 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-196">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6885-197">이미 종료 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-198">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6885-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6885-199">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-200">수신/전송 되는 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="d6885-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="d6885-201">모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-202">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-203">시도 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-204">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6885-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6885-205">설정 된 수신/발신 인스턴트 메시지의 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-206">**앱 공유 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-207"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-208"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-209">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6885-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6885-210">진행 중인 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-211">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6885-212">이미 종료 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-213">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6885-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6885-214">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-215">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-216">시도 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-217">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6885-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6885-218">설정 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-219">**통화 정보를 ca**</span><span class="sxs-lookup"><span data-stu-id="d6885-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-220"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-221"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-222">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6885-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6885-223">현재 진행 중인 수신/발신 공중 전화망 (PSTN) 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-224">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6885-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6885-225">이미 종료 된 수신/발신 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-226">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6885-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6885-227">시도 된 총 수신/발신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-228">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6885-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6885-229">설정 된 총 수신/발신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-230">**전화 회의 정보**</span><span class="sxs-lookup"><span data-stu-id="d6885-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-231"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-232"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-233">활성 인스턴트 메시징 회의</span><span class="sxs-lookup"><span data-stu-id="d6885-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6885-234">진행 중인 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-235">활성 오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="d6885-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6885-236">진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-237">활성 응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="d6885-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6885-238">진행 중인 총 응용 프로그램 공유 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-239">참가자 수</span><span class="sxs-lookup"><span data-stu-id="d6885-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="d6885-240">현재 회의에 연결 된 총 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6885-241">전화 회의 일정 오류</span><span class="sxs-lookup"><span data-stu-id="d6885-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="d6885-242">회의를 예약 하려고 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-243">전화 회의 참가 실패</span><span class="sxs-lookup"><span data-stu-id="d6885-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="d6885-244">전화 회의에 연결 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6885-245">**C 및 WA 클라이언트 카운터**</span><span class="sxs-lookup"><span data-stu-id="d6885-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6885-246"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6885-247"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6885-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6885-248">성공한 IMMCU 조인의 총 수</span><span class="sxs-lookup"><span data-stu-id="d6885-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6885-249">가입한 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6885-250">성공한 총 DMCU 조인 수</span><span class="sxs-lookup"><span data-stu-id="d6885-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6885-251">참가 한 총 A/V 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6885-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

