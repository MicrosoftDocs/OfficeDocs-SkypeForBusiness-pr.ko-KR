---
title: 'Lync Server 2013: AppSharingStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="1b396-102">Lync Server 2013의 AppSharingStream 테이블</span><span class="sxs-lookup"><span data-stu-id="1b396-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b396-103">_**마지막으로 수정한 주제:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="1b396-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="1b396-104">AppSharingStream 테이블에는 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="1b396-105">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b396-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1b396-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1b396-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1b396-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b396-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-111">Dmtf</span><span class="sxs-lookup"><span data-stu-id="1b396-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="1b396-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="1b396-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b396-113">세션이 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-115">int</span><span class="sxs-lookup"><span data-stu-id="1b396-115">int</span></span></p></td>
<td><p><span data-ttu-id="1b396-116">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="1b396-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b396-117">동일한 날짜와 동시에 시작 된 세션을 구분 하는 데 사용 되는 순차 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="1b396-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1b396-120">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="1b396-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b396-121">통화에 사용 되는 영상 회선 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="1b396-122">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b396-123">0 – 오디오</span><span class="sxs-lookup"><span data-stu-id="1b396-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="1b396-124">1-영상 통화</span><span class="sxs-lookup"><span data-stu-id="1b396-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="1b396-125">2-파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="1b396-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="1b396-126">3-응용 프로그램/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="1b396-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-128">int</span><span class="sxs-lookup"><span data-stu-id="1b396-128">int</span></span></p></td>
<td><p><span data-ttu-id="1b396-129">주요한</span><span class="sxs-lookup"><span data-stu-id="1b396-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b396-130">응용 프로그램 공유 스트림의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-132">int</span><span class="sxs-lookup"><span data-stu-id="1b396-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-133">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="1b396-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1b396-134">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-136">int</span><span class="sxs-lookup"><span data-stu-id="1b396-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-137">RTP 패킷 도착 사이에서 감지 된 최대 지터.</span><span class="sxs-lookup"><span data-stu-id="1b396-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1b396-138">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-139"><strong>왕복이</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-140">int</span><span class="sxs-lookup"><span data-stu-id="1b396-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-141">실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 평균 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="1b396-142">200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1b396-143">높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="1b396-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="1b396-144">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-146">int</span><span class="sxs-lookup"><span data-stu-id="1b396-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-147">실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 최대 양 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="1b396-148">200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1b396-149">높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="1b396-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="1b396-150">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-152">o</span><span class="sxs-lookup"><span data-stu-id="1b396-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-153">RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="1b396-154">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="1b396-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="1b396-155">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-157">o</span><span class="sxs-lookup"><span data-stu-id="1b396-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-158">RTP (실시간 전송 프로토콜) 패킷 손실의 최대 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="1b396-159">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="1b396-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="1b396-160">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-162">int</span><span class="sxs-lookup"><span data-stu-id="1b396-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-163">전송 된 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-165">int</span><span class="sxs-lookup"><span data-stu-id="1b396-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-166">세션이 끝날 때 사용 가능한 예상 단방향 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="1b396-167">초당 비트 수로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-169">int</span><span class="sxs-lookup"><span data-stu-id="1b396-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-170">응용 프로그램 공유 페이로드에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-172">o</span><span class="sxs-lookup"><span data-stu-id="1b396-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-173">단방향 총 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-173">Total amount of one-way latency.</span></span> <span data-ttu-id="1b396-174">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-176">o</span><span class="sxs-lookup"><span data-stu-id="1b396-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-177">평균 단방향 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-177">Average amount of one-way latency.</span></span> <span data-ttu-id="1b396-178">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-180">o</span><span class="sxs-lookup"><span data-stu-id="1b396-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-181">단방향 대기 시간의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="1b396-182">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-184">int</span><span class="sxs-lookup"><span data-stu-id="1b396-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-185">전체 단방향 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="1b396-186">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b396-187">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-189">o</span><span class="sxs-lookup"><span data-stu-id="1b396-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-190">전체 단방향 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-190">Total one-way burst density.</span></span> <span data-ttu-id="1b396-191">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b396-192">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-194">o</span><span class="sxs-lookup"><span data-stu-id="1b396-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-195">전체 단방향 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-195">Total one-way burst duration.</span></span> <span data-ttu-id="1b396-196">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b396-197">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-199">int</span><span class="sxs-lookup"><span data-stu-id="1b396-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-200">전체 단방향 간격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="1b396-201">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b396-202">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-204">o</span><span class="sxs-lookup"><span data-stu-id="1b396-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-205">전체 단방향 간격 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-205">Total one-way gap density.</span></span> <span data-ttu-id="1b396-206">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b396-207">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-209">o</span><span class="sxs-lookup"><span data-stu-id="1b396-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-210">전체 단방향 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-210">Total one-way gap duration.</span></span> <span data-ttu-id="1b396-211">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b396-212">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="1b396-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-215">응용 프로그램 역할 (공유자 또는 뷰어) 및 콘텐츠 형식.</span><span class="sxs-lookup"><span data-stu-id="1b396-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-217">o</span><span class="sxs-lookup"><span data-stu-id="1b396-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-218">RDP (원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-219">합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-221">o</span><span class="sxs-lookup"><span data-stu-id="1b396-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-222">RDP (원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-223">합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-225">o</span><span class="sxs-lookup"><span data-stu-id="1b396-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-226">RDP (원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-227">합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-229">int</span><span class="sxs-lookup"><span data-stu-id="1b396-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-230">RDP (원격 데스크톱 프로토콜) 타일에 대해 처리 시간에 걸리는 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-231">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-233">o</span><span class="sxs-lookup"><span data-stu-id="1b396-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-234">RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-235">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-237">o</span><span class="sxs-lookup"><span data-stu-id="1b396-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-238">RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-239">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-241">int</span><span class="sxs-lookup"><span data-stu-id="1b396-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-242">RDP (원격 데스크톱 프로토콜) 타일에 대 한 처리 시간 간격</span><span class="sxs-lookup"><span data-stu-id="1b396-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-244">o</span><span class="sxs-lookup"><span data-stu-id="1b396-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-245">RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-246">낮은 간격 밀도는 더 나은 시청 환경을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-248">o</span><span class="sxs-lookup"><span data-stu-id="1b396-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-249">RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b396-250">짧은 간격 기간은 더 나은 시청 환경과 동등 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-252">o</span><span class="sxs-lookup"><span data-stu-id="1b396-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-253">캡처된 타일의 총 속도 (타일/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-255">o</span><span class="sxs-lookup"><span data-stu-id="1b396-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-256">캡처된 타일의 평균 비율 (초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-258">o</span><span class="sxs-lookup"><span data-stu-id="1b396-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-259">캡처한 타일의 최대 속도 (초 당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-261">t</span><span class="sxs-lookup"><span data-stu-id="1b396-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-262">캡처된 타일의 속도 (초 당 타일 단위)의 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-264">o</span><span class="sxs-lookup"><span data-stu-id="1b396-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-265">캡처한 타일 속도의 버스트 밀도 (초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-267">o</span><span class="sxs-lookup"><span data-stu-id="1b396-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-268">캡처된 타일의 속도 (초당 타일 단위)로 버스트 기간을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-270">int</span><span class="sxs-lookup"><span data-stu-id="1b396-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-271">캡처된 타일의 비율 (초 당 타일 단위) 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-273">o</span><span class="sxs-lookup"><span data-stu-id="1b396-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-274">캡처된 타일의 비율 (초당 타일 수)의 간격 밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-276">o</span><span class="sxs-lookup"><span data-stu-id="1b396-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-277">캡처된 타일의 비율 (초당 타일 단위) 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-279">o</span><span class="sxs-lookup"><span data-stu-id="1b396-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-280">Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 총 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-282">o</span><span class="sxs-lookup"><span data-stu-id="1b396-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-283">Viewer에 도달 하지 않은 콘텐츠의 평균 백분율이 며, 그 대신 삭제 되 고 새 콘텐츠가 덮어쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-285">o</span><span class="sxs-lookup"><span data-stu-id="1b396-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-286">Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 최대 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-288">int</span><span class="sxs-lookup"><span data-stu-id="1b396-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-289">Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 발생</span><span class="sxs-lookup"><span data-stu-id="1b396-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-291">o</span><span class="sxs-lookup"><span data-stu-id="1b396-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-292">Viewer에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-294">o</span><span class="sxs-lookup"><span data-stu-id="1b396-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-295">Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-297">int</span><span class="sxs-lookup"><span data-stu-id="1b396-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-298">표시기에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-300">o</span><span class="sxs-lookup"><span data-stu-id="1b396-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-301">Viewer에 도달 하지는 않지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 조밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-303">o</span><span class="sxs-lookup"><span data-stu-id="1b396-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-304">Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-306">o</span><span class="sxs-lookup"><span data-stu-id="1b396-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-307">그래픽 원본에서 scraped 총 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-309">o</span><span class="sxs-lookup"><span data-stu-id="1b396-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-310">그래픽 원본에서 scraped 평균 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-312">o</span><span class="sxs-lookup"><span data-stu-id="1b396-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-313">그래픽 원본에서 scraped 최대 프레임 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-315">int</span><span class="sxs-lookup"><span data-stu-id="1b396-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-316">그래픽 원본에서 scraped 프레임의 버스트 발생</span><span class="sxs-lookup"><span data-stu-id="1b396-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-318">o</span><span class="sxs-lookup"><span data-stu-id="1b396-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-319">그래픽 원본에서 scraped 프레임의 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-321">o</span><span class="sxs-lookup"><span data-stu-id="1b396-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-322">그래픽 원본에서 scraped 프레임의 버스트 지속 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-324">int</span><span class="sxs-lookup"><span data-stu-id="1b396-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-325">그래픽 원본에서 프레임의 간격 scraped.</span><span class="sxs-lookup"><span data-stu-id="1b396-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-327">o</span><span class="sxs-lookup"><span data-stu-id="1b396-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-328">그래픽 원본에서 scraped 프레임의 간격 조밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-330">o</span><span class="sxs-lookup"><span data-stu-id="1b396-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-331">그래픽 원본에서 scraped 프레임의 간격 지속 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-333">o</span><span class="sxs-lookup"><span data-stu-id="1b396-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-334">뷰어에서 받은 총 수신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-336">o</span><span class="sxs-lookup"><span data-stu-id="1b396-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-337">뷰어에서 받은 수신 프레임의 평균 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-339">o</span><span class="sxs-lookup"><span data-stu-id="1b396-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-340">뷰어에서 수신 된 최대 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-342">int</span><span class="sxs-lookup"><span data-stu-id="1b396-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-343">뷰어에서 받은 들어오는 타일 속도의 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-345">o</span><span class="sxs-lookup"><span data-stu-id="1b396-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-346">뷰어에서 받은 들어오는 타일 속도의 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-348">o</span><span class="sxs-lookup"><span data-stu-id="1b396-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-349">뷰어에서 받은 들어오는 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-351">int</span><span class="sxs-lookup"><span data-stu-id="1b396-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-352">Viewer에서 받은 들어오는 타일 속도의 간격 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-354">o</span><span class="sxs-lookup"><span data-stu-id="1b396-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-355">뷰어에서 받은 들어오는 타일 속도의 간격 밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-357">o</span><span class="sxs-lookup"><span data-stu-id="1b396-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-358">뷰어에서 받은 들어오는 타일 속도의 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-360">o</span><span class="sxs-lookup"><span data-stu-id="1b396-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-361">뷰어에서 받은 총 수신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-363">o</span><span class="sxs-lookup"><span data-stu-id="1b396-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-364">뷰어에서 받은 수신 프레임의 평균 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-366">o</span><span class="sxs-lookup"><span data-stu-id="1b396-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-367">뷰어에서 받은 최대 수신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-369">int</span><span class="sxs-lookup"><span data-stu-id="1b396-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-370">뷰어에서 받은 들어오는 프레임 속도의 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-372">o</span><span class="sxs-lookup"><span data-stu-id="1b396-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-373">뷰어에서 받은 들어오는 프레임 속도의 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="1b396-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-375">o</span><span class="sxs-lookup"><span data-stu-id="1b396-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-376">뷰어에서 받은 들어오는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-378">int</span><span class="sxs-lookup"><span data-stu-id="1b396-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-379">뷰어에서 받은 들어오는 프레임 속도의 간격</span><span class="sxs-lookup"><span data-stu-id="1b396-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-381">o</span><span class="sxs-lookup"><span data-stu-id="1b396-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-382">뷰어에서 받은 들어오는 프레임 속도의 간격 밀도</span><span class="sxs-lookup"><span data-stu-id="1b396-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-384">o</span><span class="sxs-lookup"><span data-stu-id="1b396-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-385">뷰어에서 받은 들어오는 프레임 속도의 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-387">o</span><span class="sxs-lookup"><span data-stu-id="1b396-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-388">보낸 사람의 총 송신 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-390">o</span><span class="sxs-lookup"><span data-stu-id="1b396-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-391">보낸 사람에 대 한 송신 타일 속도의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-393">o</span><span class="sxs-lookup"><span data-stu-id="1b396-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-394">보낸 사람의 최대 보내는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-396">int</span><span class="sxs-lookup"><span data-stu-id="1b396-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-397">보낸 사람에 대 한 보내는 타일 속도의 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-399">o</span><span class="sxs-lookup"><span data-stu-id="1b396-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-400">보낸 사람에 대 한 송신 타일 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-402">o</span><span class="sxs-lookup"><span data-stu-id="1b396-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-403">보낸 사람에 대 한 송신 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-405">int</span><span class="sxs-lookup"><span data-stu-id="1b396-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-406">보낸 사람에 대 한 보내는 타일 속도의 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-408">o</span><span class="sxs-lookup"><span data-stu-id="1b396-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-409">보낸 사람에 대 한 송신 타일 속도의 간격 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-411">o</span><span class="sxs-lookup"><span data-stu-id="1b396-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-412">보낸 사람에 대 한 보내는 타일 속도의 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-414">o</span><span class="sxs-lookup"><span data-stu-id="1b396-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-415">보낸 사람의 총 송신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-417">o</span><span class="sxs-lookup"><span data-stu-id="1b396-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-418">보낸 사람의 평균 송신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-420">o</span><span class="sxs-lookup"><span data-stu-id="1b396-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-421">보낸 사람의 최대 송신 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-423">int</span><span class="sxs-lookup"><span data-stu-id="1b396-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-424">보낸 사람에 대해 보내는 프레임 속도의 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-426">o</span><span class="sxs-lookup"><span data-stu-id="1b396-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-427">보낸 사람의 보내는 프레임 속도에 대 한 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-429">o</span><span class="sxs-lookup"><span data-stu-id="1b396-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-430">보낸 사람에 대 한 보내는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-432">int</span><span class="sxs-lookup"><span data-stu-id="1b396-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-433">보낸 사람에 대해 보내는 프레임 속도의 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-435">o</span><span class="sxs-lookup"><span data-stu-id="1b396-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-436">보낸 사람의 보내는 프레임 속도에 대 한 간격 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-438">o</span><span class="sxs-lookup"><span data-stu-id="1b396-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-439">보낸 사람의 보내는 프레임 속도에 대 한 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-441">int</span><span class="sxs-lookup"><span data-stu-id="1b396-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-442">평균 비디오 해상도 높이 (픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-444">int</span><span class="sxs-lookup"><span data-stu-id="1b396-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-445">평균 비디오 해상도 너비 (픽셀 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-446"><strong>Ipsec</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-447">다소</span><span class="sxs-lookup"><span data-stu-id="1b396-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-448">인바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b396-449"><strong>위한</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-450">다소</span><span class="sxs-lookup"><span data-stu-id="1b396-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-451">아웃 바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b396-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="1b396-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="1b396-453">다소</span><span class="sxs-lookup"><span data-stu-id="1b396-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b396-454">1은 스트림 방향이 호출자에서 피호출자로 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="1b396-455">0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b396-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

