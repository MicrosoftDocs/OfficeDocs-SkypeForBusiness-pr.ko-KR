---
title: 'Lync Server 2013: 모바일 성능 카운터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513605"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="70685-102">Lync Server 2013의 모바일 기능 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="70685-102">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70685-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="70685-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="70685-104">다음 표에는 통합 커뮤니케이션 웹 API (WA) 및 Lync Server 2013 Mcx Mobility Service를 실행 하는 서버를 모니터링 하는 데 사용할 수 있는 성능 카운터의 이름과 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70685-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="70685-105">(C) 테이블에 있는 카운터의 범주 이름은 **LS: WEB – wa**입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="70685-106">Mcx Mobility Service 테이블의 카운터에 대 한 범주 이름 **: 웹-모바일 통신 서비스**입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="70685-107">DATWA에 대 한 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="70685-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70685-108">카운터</span><span class="sxs-lookup"><span data-stu-id="70685-108">Counter</span></span></th>
<th><span data-ttu-id="70685-109">설명</span><span class="sxs-lookup"><span data-stu-id="70685-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70685-110">활성 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="70685-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="70685-111">현재 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="70685-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-112">활성 응용 프로그램 공유 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-113">현재 응용 프로그램 공유 모달의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-114">활성 오디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-115">현재 오디오 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-116">활성 데이터 공동 작업 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-117">현재 데이터 공동 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-118">Active Directory 사진 가져오기 대기 시간 (ms)</span><span class="sxs-lookup"><span data-stu-id="70685-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="70685-119">이 카운터는 active directory에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70685-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-120">활성 메시징 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-121">현재 메시징 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-122">활성 파노라마 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-123">현재 파노라마 비디오 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-124">활성 보류 중인 가져오기 수</span><span class="sxs-lookup"><span data-stu-id="70685-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="70685-125">현재 보류 중인 활성 상태 수입니다. 서버에 대 한 장기 유지 연결</span><span class="sxs-lookup"><span data-stu-id="70685-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-126">활성 세션 수</span><span class="sxs-lookup"><span data-stu-id="70685-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="70685-127">응용 프로그램당 및 total에 등록 된 현재 끝점 수</span><span class="sxs-lookup"><span data-stu-id="70685-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-128">활성 사용자 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="70685-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="70685-129">현재 사용자 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="70685-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-130">응용 프로그램이 없는 활성 사용자 인스턴스</span><span class="sxs-lookup"><span data-stu-id="70685-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="70685-131">응용 프로그램이 없는 현재 사용자 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-132">활성 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="70685-133">현재 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="70685-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-134">초당 수신 되는 응용 프로그램 만들기 요청</span><span class="sxs-lookup"><span data-stu-id="70685-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-135">받은 응용 프로그램 만들기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-136">MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="70685-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-137">MCU 연결 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-138">AV MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="70685-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-139">AV MCU 참가 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-140">평균 응용 프로그램 시작 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="70685-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="70685-141">평균 응용 프로그램 시작 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-142">평균 세션 수명 (ms)</span><span class="sxs-lookup"><span data-stu-id="70685-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="70685-143">세션의 평균 수명 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-144">데이터 MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="70685-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-145">데이터 MCU 참가 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-146">Exchange 연락처 검색 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="70685-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="70685-147">이 카운터는 Exchange에서 연락처를 검색 하는 데 걸린 평균 시간 (밀리초)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="70685-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-148">Exchange HD 사진 가져오기 대기 시간 (ms)</span><span class="sxs-lookup"><span data-stu-id="70685-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="70685-149">이 카운터는 Exchange에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70685-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-150">HTTP 4xx 응답/초</span><span class="sxs-lookup"><span data-stu-id="70685-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-151">HTTP 4xx 코드를 사용한 응답 비율 (초 단위)</span><span class="sxs-lookup"><span data-stu-id="70685-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-152">HTTP 5xx 응답/초</span><span class="sxs-lookup"><span data-stu-id="70685-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-153">HTTP 5xx 코드를 사용한 응답 비율 (초 단위)</span><span class="sxs-lookup"><span data-stu-id="70685-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-154">IM MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="70685-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-155">IM MCU 참가 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-156">Active Directory 사진 가져오기 오류 수</span><span class="sxs-lookup"><span data-stu-id="70685-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-157">Active Directory에서 사진 검색에 대 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-158">연락처 검색 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="70685-159">Exchange에서 연락처를 검색 하는 데 실패 한 총 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-160">Deserialization 오류 발생 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-161">총 deserialization 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-162">HD 사진 가져오기 실패 수</span><span class="sxs-lookup"><span data-stu-id="70685-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-163">Exchange에서 HD 사진을 검색 하는 데 실패 한 총 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-164">응용 프로그램당 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="70685-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="70685-165">응용 프로그램당 허용 되는 최대 수를 초과 하는 구독 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-166">일괄 처리당 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="70685-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="70685-167">일괄 처리당 허용 되는 최대값을 초과 하는 구독 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-168">현재 상태 구독 실패</span><span class="sxs-lookup"><span data-stu-id="70685-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-169">현재 상태 구독 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-170">끝점 오류 등록</span><span class="sxs-lookup"><span data-stu-id="70685-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="70685-171">끝점 등록 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-172">초당 수신한 요청</span><span class="sxs-lookup"><span data-stu-id="70685-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-173">수신 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-174">초당 성공한 요청</span><span class="sxs-lookup"><span data-stu-id="70685-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-175">성공한 요청의 초당 비율 (HTTP 2xx/3xx 응답 코드)</span><span class="sxs-lookup"><span data-stu-id="70685-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-176">성공한 응용 프로그램 요청 만들기/초</span><span class="sxs-lookup"><span data-stu-id="70685-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-177">성공적인 응용 프로그램 만들기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-178">보류 중인 가져오기 수 제한</span><span class="sxs-lookup"><span data-stu-id="70685-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="70685-179">시간 초과 된 보류 중인 일정의 수</span><span class="sxs-lookup"><span data-stu-id="70685-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-180">수신 되는 총 응용 프로그램 만들기 요청</span><span class="sxs-lookup"><span data-stu-id="70685-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="70685-181">서비스가 시작 된 이후 받은 총 응용 프로그램 만들기 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-182">총 HTTP 4xx 응답</span><span class="sxs-lookup"><span data-stu-id="70685-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="70685-183">총 HTTP 4xx 응답 수</span><span class="sxs-lookup"><span data-stu-id="70685-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-184">총 HTTP 5xx 응답</span><span class="sxs-lookup"><span data-stu-id="70685-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="70685-185">총 HTTP 5xx 응답 수</span><span class="sxs-lookup"><span data-stu-id="70685-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-186">명령 채널에서 받은 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="70685-187">명령 채널에서 받은 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-188">성공한 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="70685-189">성공한 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-190">시작 된 총 세션</span><span class="sxs-lookup"><span data-stu-id="70685-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="70685-191">서비스가 시작 된 이후 시작 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-192">유휴 시간 제한으로 인해 종료 된 총 세션</span><span class="sxs-lookup"><span data-stu-id="70685-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="70685-193">사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-194">총 제한 된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="70685-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="70685-195">제한 된 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="70685-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="70685-196">Mcx Mobility Service에 대 한 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="70685-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70685-197">카운터</span><span class="sxs-lookup"><span data-stu-id="70685-197">Counter</span></span></th>
<th><span data-ttu-id="70685-198">설명</span><span class="sxs-lookup"><span data-stu-id="70685-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70685-199">평균 세션 수명 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="70685-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="70685-200">세션의 평균 수명 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-201">현재 푸시 알림 구독</span><span class="sxs-lookup"><span data-stu-id="70685-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="70685-202">현재 푸시 알림 구독 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="70685-203">현재 활성 세션 수와 함께이 번호는 Windows Mobile 또는 iPhone 장치에 대해 등록 된 현재 활성 세션의 하위 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70685-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-204">현재 활성 상태인 네트워크 시간 제한 폴링 수</span><span class="sxs-lookup"><span data-stu-id="70685-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="70685-205">시간이 초과 된 네트워크 폴링 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-206">현재 활성 상태인 폴링 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="70685-207">현재 활성 상태인 폴링 (서버에 대 한 장기 유지 연결)의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-208">현재 활성 세션 수</span><span class="sxs-lookup"><span data-stu-id="70685-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="70685-209">모바일 서비스에 등록 된 현재 끝점 수</span><span class="sxs-lookup"><span data-stu-id="70685-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-210">활성 현재 상태 구독이 있는 현재 활성 상태의 세션 수</span><span class="sxs-lookup"><span data-stu-id="70685-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="70685-211">활성 현재 상태 구독이 있는 현재 활성 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-212">푸시 알림 요청 실패/초</span><span class="sxs-lookup"><span data-stu-id="70685-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-213">실패 한 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-214">초당 성공한 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-215">성공한 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-216">초당 제한 된 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-217">제한 된 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-218">푸시 알림 요청/초</span><span class="sxs-lookup"><span data-stu-id="70685-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-219">전송 된 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-220">실패 한 요청/초</span><span class="sxs-lookup"><span data-stu-id="70685-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-221">실패 한 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-222">초당 수신한 요청</span><span class="sxs-lookup"><span data-stu-id="70685-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-223">수신 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-224">거부 된 요청/초</span><span class="sxs-lookup"><span data-stu-id="70685-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-225">거부 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-226">초당 성공한 요청</span><span class="sxs-lookup"><span data-stu-id="70685-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-227">성공한 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-228">성공한 세션 요청 시작/초</span><span class="sxs-lookup"><span data-stu-id="70685-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="70685-229">성공적인 위치 가져오기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="70685-230">세션 시작 요청은 서버에서 가장 많은 CPU를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70685-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="70685-231">지원 되는 최대 부하는 12 초입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="70685-232">지속 가능성은 서버의 다른 부하에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="70685-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="70685-233">세션 시작은 일반적으로 오랜 시간 동안 로그 아웃 된 사용자에 대 한 로그인을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="70685-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-234">총 거부 되는 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="70685-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="70685-235">거절 된 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-236">총 실패 한 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="70685-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="70685-237">실패 한 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-238">총 실패 한 아웃 바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="70685-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="70685-239">실패 한 아웃 바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-240">사용자가 종료 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="70685-241">사용자가 종료 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-242">총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="70685-243">푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-244">실패 한 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="70685-245">실패 한 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-246">성공한 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="70685-247">성공한 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-248">제한 된 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="70685-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="70685-249">제한 된 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-250">실패 한 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="70685-251">실패 한 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-252">명령 채널에서 받은 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="70685-253">명령 채널에서 받은 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-254">거부 된 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="70685-255">거부 된 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-256">성공한 총 요청</span><span class="sxs-lookup"><span data-stu-id="70685-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="70685-257">모바일 서비스에 대해 성공한 요청의 총 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-258">총 세션 시작 횟수</span><span class="sxs-lookup"><span data-stu-id="70685-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="70685-259">Mobility Service를 시작한 이후 시작 된 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-260">사용자 유휴 시간 초과로 인해 종료 된 총 세션 수</span><span class="sxs-lookup"><span data-stu-id="70685-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="70685-261">사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70685-262">총 성공한 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="70685-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="70685-263">성공한 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70685-264">총 성공한 아웃 바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="70685-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="70685-265">성공한 아웃 바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70685-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

