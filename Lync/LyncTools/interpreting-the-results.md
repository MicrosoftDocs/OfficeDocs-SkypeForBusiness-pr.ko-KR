---
title: 결과 해석
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484f10757dcbd1463b54cf70ac8d725402decb44
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="d6036-102">결과 해석</span><span class="sxs-lookup"><span data-stu-id="d6036-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6036-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d6036-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d6036-104">Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)에는 클라이언트가 수행 하는 작업과 문제가 발생 하는지 여부를 이해 하는 데 사용할 수 있는 여러 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="d6036-105">클라이언트 카운터</span><span class="sxs-lookup"><span data-stu-id="d6036-105">Client Counters</span></span>

<span data-ttu-id="d6036-106">실행 중인 LyncPerfTool 각 인스턴스에는 별도의 카운터 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="d6036-107">각 인스턴스의 이름은 해당 프로세스 ID에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="d6036-108">클라이언트가 오버 로드 되 면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="d6036-109">이러한 문제를 방지 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="d6036-110">클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="d6036-111">CPU가 지속적으로 90% 이상 지속 되 면 사용자 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="d6036-112">메모리 공간이 높으면 페이지 파일 크기가 충분 하지 않은 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="d6036-113">컴퓨터에서 커밋 충전량이 한도를 적중 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="d6036-114">메모리 제한으로 실행 하는 경우에는 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="d6036-115">다음 표에서는 키 LyncPerfTool 성능 카운터를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="d6036-116">**일반 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-117"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-118"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-119">소요 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d6036-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="d6036-120">프로세스를 시작한 후 소요 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-121">활성 끝점</span><span class="sxs-lookup"><span data-stu-id="d6036-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="d6036-122">현재 서버에 연결 되어 있는 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-123">실패 한 로그온</span><span class="sxs-lookup"><span data-stu-id="d6036-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="d6036-124">끝점 로그인 실패의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-125">로그온 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="d6036-126">끝점 로그인 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-127">끝점 연결 끊기</span><span class="sxs-lookup"><span data-stu-id="d6036-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="d6036-128">연결을 끊은 총 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-129">**현재 상태 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-130"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-131"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-132">SetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="d6036-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="d6036-133">현재 상태 변경 시도 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-133">Total number of presence change attempts.</span></span> <span data-ttu-id="d6036-134">다른 유형의 현재 변경 내용은 SetPresence 상태 (현재 유형) 통화 성능 카운터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6036-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-135">NNN 현재 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="d6036-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="d6036-136">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-137">GetPresence 상태 통화</span><span class="sxs-lookup"><span data-stu-id="d6036-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="d6036-138">현재 상태 요청 시도의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-139">NNN-GetPresence 상태에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="d6036-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="d6036-140">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-141">**주소록 서비스 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-141">**Address Book service Information**</span></span>

<span data-ttu-id="d6036-142">이 범주에는 ABS (주소록 서비스) 파일 다운로드 및 주소록 웹 쿼리 서비스 요청을 모니터링 하는 데 사용 되는 카운터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-143"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-144"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-145">ABS 전체/델타 파일 다운로드 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-146">시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-147">ABS 전체/델타 파일 다운로드 성공</span><span class="sxs-lookup"><span data-stu-id="d6036-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6036-148">시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-149">주소록 웹 쿼리 서비스 관련 카운터</span><span class="sxs-lookup"><span data-stu-id="d6036-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="d6036-150">주소록 파일 다운로드 관련 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-151">ABS WS 호출이 시도 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-152">시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-153">ABS WS 호출이 성공 함</span><span class="sxs-lookup"><span data-stu-id="d6036-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6036-154">성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-155">ABS WS 호출이 실패 함</span><span class="sxs-lookup"><span data-stu-id="d6036-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="d6036-156">오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-157">**메일 그룹 (DL) 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-158"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-159"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-160">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="d6036-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-161">시도 된 DLX (총 메일 그룹 확장) 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-162">통화 성공</span><span class="sxs-lookup"><span data-stu-id="d6036-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6036-163">성공적인 응답 코드를 반환한 총 DLX web service 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-164">통화 실패</span><span class="sxs-lookup"><span data-stu-id="d6036-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="d6036-165">오류 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-166">**VoIP 기본 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="d6036-167">이 시나리오를 사용 하도록 설정 하는 경우 중재 서버, A/V 회의 서버,에 지 서버, 응답 그룹 응용 프로그램 및 전화 회의 자동 전화 교환에 대 한 호출을 비롯 하 여 모든 VoIP (Voice over IP) 통화에 대 한 보고서 번호 아래에 나열 된 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="d6036-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-168"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-169"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-170">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6036-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6036-171">현재 진행 중인 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-172">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6036-173">이미 종료 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-174">통화가 거절 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="d6036-175">거절 된 들어오는 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-176">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-177">시도 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-178">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6036-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6036-179">설정 된 수신/발신 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-180">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6036-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6036-181">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-182">VoIP 통과 속도 (%)</span><span class="sxs-lookup"><span data-stu-id="d6036-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="d6036-183">총 통화 횟수 설정/총 통화를 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-184">**응답 그룹 서비스 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-185"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-186"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-187">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6036-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6036-188">응답 그룹 응용 프로그램에 대 한 총 활성 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-189">시도한 통화</span><span class="sxs-lookup"><span data-stu-id="d6036-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-190">시도한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-191">**IM (인스턴트 메시징) 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-192"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-193"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-194">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6036-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6036-195">진행 된 수신/발신 인스턴트 메시징 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-196">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6036-197">이미 종료 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-198">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6036-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6036-199">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-200">수신/전송 되는 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="d6036-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="d6036-201">모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-202">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-203">시도 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-204">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6036-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6036-205">설정 된 수신/발신 인스턴트 메시지의 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-206">**앱 공유 통화 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-207"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-208"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-209">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6036-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6036-210">진행 중인 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-211">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6036-212">이미 종료 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-213">호출 되는 NNN</span><span class="sxs-lookup"><span data-stu-id="d6036-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="d6036-214">서버에서 받은 총 nnn 응답 코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-215">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-216">시도 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-217">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6036-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6036-218">설정 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-219">**통화 정보를 ca**</span><span class="sxs-lookup"><span data-stu-id="d6036-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-220"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-221"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-222">통화 활성</span><span class="sxs-lookup"><span data-stu-id="d6036-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="d6036-223">현재 진행 중인 수신/발신 공중 전화망 (PSTN) 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-224">통화가 종료 됨</span><span class="sxs-lookup"><span data-stu-id="d6036-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="d6036-225">이미 종료 된 수신/발신 PSTN 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-226">수신/발신 전화 시도</span><span class="sxs-lookup"><span data-stu-id="d6036-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="d6036-227">시도 된 총 수신/발신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-228">수신/발신 전화</span><span class="sxs-lookup"><span data-stu-id="d6036-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="d6036-229">설정 된 총 수신/발신 PSTN 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-230">**전화 회의 정보**</span><span class="sxs-lookup"><span data-stu-id="d6036-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-231"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-232"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-233">활성 인스턴트 메시징 회의</span><span class="sxs-lookup"><span data-stu-id="d6036-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6036-234">진행 중인 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-235">활성 오디오/비디오 회의</span><span class="sxs-lookup"><span data-stu-id="d6036-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6036-236">진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-237">활성 응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="d6036-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="d6036-238">진행 중인 총 응용 프로그램 공유 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-239">참가자 수</span><span class="sxs-lookup"><span data-stu-id="d6036-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="d6036-240">현재 회의에 연결 된 총 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6036-241">전화 회의 일정 오류</span><span class="sxs-lookup"><span data-stu-id="d6036-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="d6036-242">회의를 예약 하려고 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-243">전화 회의 참가 실패</span><span class="sxs-lookup"><span data-stu-id="d6036-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="d6036-244">전화 회의에 연결 하는 동안 발생 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6036-245">**C 및 WA 클라이언트 카운터**</span><span class="sxs-lookup"><span data-stu-id="d6036-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6036-246"><strong>성능 카운터</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="d6036-247"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="d6036-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6036-248">성공한 IMMCU 조인의 총 수</span><span class="sxs-lookup"><span data-stu-id="d6036-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6036-249">가입한 총 인스턴트 메시징 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6036-250">성공한 총 DMCU 조인 수</span><span class="sxs-lookup"><span data-stu-id="d6036-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d6036-251">참가 한 총 A/V 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6036-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

