---
title: 'Lync Server 2013: 모바일 성능 카운터'
description: 'Lync Server 2013: 모바일 성능 카운터'
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
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550534"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="2efe3-103">Lync Server 2013의 모바일 기능 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="2efe3-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2efe3-104">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2efe3-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2efe3-105">다음 표에는 통합 커뮤니케이션 웹 API (WA) 및 Lync Server 2013 Mcx Mobility Service를 실행 하는 서버를 모니터링 하는 데 사용할 수 있는 성능 카운터의 이름과 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="2efe3-106">(C) 테이블에 있는 카운터의 범주 이름은 **LS: WEB – wa**입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="2efe3-107">Mcx Mobility Service 테이블의 카운터에 대 한 범주 이름 **: 웹-모바일 통신 서비스**입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="2efe3-108">DATWA에 대 한 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="2efe3-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2efe3-109">카운터</span><span class="sxs-lookup"><span data-stu-id="2efe3-109">Counter</span></span></th>
<th><span data-ttu-id="2efe3-110">설명</span><span class="sxs-lookup"><span data-stu-id="2efe3-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-111">활성 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-112">현재 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-113">활성 응용 프로그램 공유 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-114">현재 응용 프로그램 공유 모달의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-115">활성 오디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-116">현재 오디오 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-117">활성 데이터 공동 작업 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-118">현재 데이터 공동 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-119">Active Directory 사진 가져오기 대기 시간 (ms)</span><span class="sxs-lookup"><span data-stu-id="2efe3-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2efe3-120">이 카운터는 active directory에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-121">활성 메시징 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-122">현재 메시징 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-123">활성 파노라마 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-124">현재 파노라마 비디오 모달 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-125">활성 보류 중인 가져오기 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-126">현재 보류 중인 활성 상태 수입니다. 서버에 대 한 장기 유지 연결</span><span class="sxs-lookup"><span data-stu-id="2efe3-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-127">활성 세션 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-128">응용 프로그램당 및 total에 등록 된 현재 끝점 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-129">활성 사용자 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-130">현재 사용자 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-131">응용 프로그램이 없는 활성 사용자 인스턴스</span><span class="sxs-lookup"><span data-stu-id="2efe3-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="2efe3-132">응용 프로그램이 없는 현재 사용자 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-133">활성 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-134">현재 비디오 모달 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-135">초당 수신 되는 응용 프로그램 만들기 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-136">받은 응용 프로그램 만들기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-137">MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="2efe3-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-138">MCU 연결 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-139">AV MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="2efe3-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-140">AV MCU 참가 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-141">평균 응용 프로그램 시작 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="2efe3-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="2efe3-142">평균 응용 프로그램 시작 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-143">평균 세션 수명 (ms)</span><span class="sxs-lookup"><span data-stu-id="2efe3-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="2efe3-144">세션의 평균 수명 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-145">데이터 MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="2efe3-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-146">데이터 MCU 참가 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-147">Exchange 연락처 검색 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="2efe3-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2efe3-148">이 카운터는 Exchange에서 연락처를 검색 하는 데 걸린 평균 시간 (밀리초)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-149">Exchange HD 사진 가져오기 대기 시간 (ms)</span><span class="sxs-lookup"><span data-stu-id="2efe3-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2efe3-150">이 카운터는 Exchange에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-151">HTTP 4xx 응답/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-152">HTTP 4xx 코드를 사용한 응답 비율 (초 단위)</span><span class="sxs-lookup"><span data-stu-id="2efe3-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-153">HTTP 5xx 응답/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-154">HTTP 5xx 코드를 사용한 응답 비율 (초 단위)</span><span class="sxs-lookup"><span data-stu-id="2efe3-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-155">IM MCU 참가 실패</span><span class="sxs-lookup"><span data-stu-id="2efe3-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-156">IM MCU 참가 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-157">Active Directory 사진 가져오기 오류 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-158">Active Directory에서 사진 검색에 대 한 총 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-159">연락처 검색 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-160">Exchange에서 연락처를 검색 하는 데 실패 한 총 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-161">Deserialization 오류 발생 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-162">총 deserialization 실패 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-163">HD 사진 가져오기 실패 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-164">Exchange에서 HD 사진을 검색 하는 데 실패 한 총 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-165">응용 프로그램당 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="2efe3-166">응용 프로그램당 허용 되는 최대 수를 초과 하는 구독 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-167">일괄 처리당 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="2efe3-168">일괄 처리당 허용 되는 최대값을 초과 하는 구독 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-169">현재 상태 구독 실패</span><span class="sxs-lookup"><span data-stu-id="2efe3-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-170">현재 상태 구독 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-171">끝점 오류 등록</span><span class="sxs-lookup"><span data-stu-id="2efe3-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="2efe3-172">끝점 등록 실패 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-173">초당 수신한 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-174">수신 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-175">초당 성공한 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-176">성공한 요청의 초당 비율 (HTTP 2xx/3xx 응답 코드)</span><span class="sxs-lookup"><span data-stu-id="2efe3-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-177">성공한 응용 프로그램 요청 만들기/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-178">성공적인 응용 프로그램 만들기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-179">보류 중인 가져오기 수 제한</span><span class="sxs-lookup"><span data-stu-id="2efe3-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-180">시간 초과 된 보류 중인 일정의 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-181">수신 되는 총 응용 프로그램 만들기 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="2efe3-182">서비스가 시작 된 이후 받은 총 응용 프로그램 만들기 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-183">총 HTTP 4xx 응답</span><span class="sxs-lookup"><span data-stu-id="2efe3-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="2efe3-184">총 HTTP 4xx 응답 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-185">총 HTTP 5xx 응답</span><span class="sxs-lookup"><span data-stu-id="2efe3-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="2efe3-186">총 HTTP 5xx 응답 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-187">명령 채널에서 받은 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="2efe3-188">명령 채널에서 받은 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-189">성공한 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2efe3-190">성공한 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-191">시작 된 총 세션</span><span class="sxs-lookup"><span data-stu-id="2efe3-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="2efe3-192">서비스가 시작 된 이후 시작 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-193">유휴 시간 제한으로 인해 종료 된 총 세션</span><span class="sxs-lookup"><span data-stu-id="2efe3-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="2efe3-194">사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-195">총 제한 된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2efe3-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="2efe3-196">제한 된 응용 프로그램 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="2efe3-197">Mcx Mobility Service에 대 한 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="2efe3-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2efe3-198">카운터</span><span class="sxs-lookup"><span data-stu-id="2efe3-198">Counter</span></span></th>
<th><span data-ttu-id="2efe3-199">설명</span><span class="sxs-lookup"><span data-stu-id="2efe3-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-200">평균 세션 수명 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="2efe3-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="2efe3-201">세션의 평균 수명 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-202">현재 푸시 알림 구독</span><span class="sxs-lookup"><span data-stu-id="2efe3-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="2efe3-203">현재 푸시 알림 구독 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="2efe3-204">현재 활성 세션 수와 함께이 번호는 Windows Mobile 또는 iPhone 장치에 대해 등록 된 현재 활성 세션의 하위 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-205">현재 활성 상태인 네트워크 시간 제한 폴링 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-206">시간이 초과 된 네트워크 폴링 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-207">현재 활성 상태인 폴링 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-208">현재 활성 상태인 폴링 (서버에 대 한 장기 유지 연결)의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-209">현재 활성 세션 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-210">모바일 서비스에 등록 된 현재 끝점 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-211">활성 현재 상태 구독이 있는 현재 활성 상태의 세션 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="2efe3-212">활성 현재 상태 구독이 있는 현재 활성 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-213">푸시 알림 요청 실패/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-214">실패 한 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-215">초당 성공한 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-216">성공한 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-217">초당 제한 된 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-218">제한 된 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-219">푸시 알림 요청/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-220">전송 된 푸시 알림의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-221">실패 한 요청/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-222">실패 한 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-223">초당 수신한 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-224">수신 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-225">거부 된 요청/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-226">거부 된 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-227">초당 성공한 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-228">성공한 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-229">성공한 세션 요청 시작/초</span><span class="sxs-lookup"><span data-stu-id="2efe3-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2efe3-230">성공적인 위치 가져오기 요청의 초당 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-230">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="2efe3-231">세션 시작 요청은 서버에서 가장 많은 CPU를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-231">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="2efe3-232">지원 되는 최대 부하는 12 초입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-232">Peak supported load is 12/second.</span></span> <span data-ttu-id="2efe3-233">지속 가능성은 서버의 다른 부하에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-233">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="2efe3-234">세션 시작은 일반적으로 오랜 시간 동안 로그 아웃 된 사용자에 대 한 로그인을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-234">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-235">총 거부 되는 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="2efe3-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2efe3-236">거절 된 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-237">총 실패 한 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="2efe3-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2efe3-238">실패 한 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-239">총 실패 한 아웃 바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="2efe3-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2efe3-240">실패 한 아웃 바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-241">사용자가 종료 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="2efe3-242">사용자가 종료 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-243">총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="2efe3-244">푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-245">실패 한 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="2efe3-246">실패 한 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-247">성공한 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2efe3-248">성공한 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-249">제한 된 총 푸시 알림 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="2efe3-250">제한 된 푸시 알림 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-251">실패 한 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="2efe3-252">실패 한 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-253">명령 채널에서 받은 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="2efe3-254">명령 채널에서 받은 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-255">거부 된 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="2efe3-256">거부 된 요청의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-257">성공한 총 요청</span><span class="sxs-lookup"><span data-stu-id="2efe3-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2efe3-258">모바일 서비스에 대해 성공한 요청의 총 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-259">총 세션 시작 횟수</span><span class="sxs-lookup"><span data-stu-id="2efe3-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="2efe3-260">Mobility Service를 시작한 이후 시작 된 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-261">사용자 유휴 시간 초과로 인해 종료 된 총 세션 수</span><span class="sxs-lookup"><span data-stu-id="2efe3-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="2efe3-262">사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efe3-263">총 성공한 인바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="2efe3-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2efe3-264">성공한 인바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efe3-265">총 성공한 아웃 바운드 음성 통화</span><span class="sxs-lookup"><span data-stu-id="2efe3-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2efe3-266">성공한 아웃 바운드 음성 통화의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2efe3-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

