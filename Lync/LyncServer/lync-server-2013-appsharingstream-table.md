---
title: 'Lync Server 2013: AppSharingStream 테이블'
description: 'Lync Server 2013: AppSharingStream 테이블'
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
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574724"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="b7c23-103">Lync Server 2013의 AppSharingStream 테이블</span><span class="sxs-lookup"><span data-stu-id="b7c23-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7c23-104">_**마지막으로 수정 된 항목:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="b7c23-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="b7c23-105">AppSharingStream 테이블은 응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="b7c23-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7c23-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b7c23-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b7c23-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b7c23-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="b7c23-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="b7c23-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="b7c23-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b7c23-114">세션이 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-116">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-116">int</span></span></p></td>
<td><p><span data-ttu-id="b7c23-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="b7c23-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b7c23-118">같은 날짜와 시간에 시작된 세션을 구분하는 데 사용되는 순차 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b7c23-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b7c23-121">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="b7c23-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b7c23-p102">통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b7c23-124">0-오디오</span><span class="sxs-lookup"><span data-stu-id="b7c23-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="b7c23-125">1-비디오</span><span class="sxs-lookup"><span data-stu-id="b7c23-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="b7c23-126">2 -- 파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="b7c23-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="b7c23-127">3-응용 프로그램/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="b7c23-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-129">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-129">int</span></span></p></td>
<td><p><span data-ttu-id="b7c23-130">Primary</span><span class="sxs-lookup"><span data-stu-id="b7c23-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="b7c23-131">응용 프로그램 공유 스트림의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-133">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-134">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b7c23-135">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-137">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-138">RTP 패킷 도착 시간 사이에 발견된 최대 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b7c23-139">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-140"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-141">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p105">RTP(Real-time Transport Protocol) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b7c23-p106">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-147">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p107">실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 최대 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b7c23-p108">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-153">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p109">RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-158">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p110">RTP(Real-time Transport Protocol) 패킷 손실의 최대 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-163">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-164">보낸 패킷의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-165"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-166">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p111">세션 종료 시 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-170">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-171">응용 프로그램 공유 페이로드의 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-173">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p112">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-177">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p113">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-181">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p114">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-185">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p115">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-190">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p116">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-195">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p117">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-200">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p118">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-205">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p119">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-210">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p120">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="b7c23-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-216">응용 프로그램 역할(공유자 또는 보기 권한자) 및 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-218">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p121">RDP(원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-222">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p122">RDP(원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-226">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p123">RDP(원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-230">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p124">RDP(원격 데스크톱 프로토콜) 타일의 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-234">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p125">RDP(원격 데스크톱 프로토콜) 타일의 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-238">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p126">RDP(원격 데스크톱 프로토콜) 타일의 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-242">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-243">RDP(원격 데스크톱 프로토콜) 타일의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-245">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p127">RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 밀도입니다. 갭 밀도가 낮으면 보기 환경 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-249">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-p128">RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 기간입니다. 갭 기간이 짧으면 보기 환경 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-253">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-254">캡처된 타일의 총 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-256">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-257">캡처된 타일의 평균 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-259">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-260">캡처된 타일의 최대 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-262">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-263">캡처된 타일 속도의 버스트 발생 수(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-265">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-266">캡처된 타일 속도의 버스트 밀도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-268">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-269">캡처된 타일 속도의 버스트 기간(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-271">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-272">캡처된 타일 속도의 갭 발생 수(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-274">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-275">캡처된 타일 속도의 갭 밀도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-277">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-278">캡처된 타일 속도의 갭 기간(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-280">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-281">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 총 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-283">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-284">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-286">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-287">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 최대 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-289">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-290">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-292">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-293">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-295">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-296">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-298">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-299">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-301">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-302">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-304">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-305">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-307">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-308">그래픽 원본에서 스크랩된 총 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-310">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-311">그래픽 원본에서 스크랩된 평균 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-313">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-314">그래픽 원본에서 스크랩된 최대 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-316">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-317">그래픽 원본에서 스크랩된 프레임의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-319">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-320">그래픽 원본에서 스크랩된 프레임의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-322">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-323">그래픽 원본에서 스크랩된 프레임의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-325">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-326">그래픽 원본에서 스크랩된 프레임의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-328">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-329">그래픽 원본에서 스크랩된 프레임의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-331">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-332">그래픽 원본에서 스크랩된 프레임의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-334">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-335">보기 권한자가 받은 총 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-337">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-338">보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-340">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-341">보기 권한자가 받은 최대 들어오는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-343">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-344">보기 권한자가 받은 들어오는 타일 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-346">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-347">보기 권한자가 받은 들어오는 타일 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-349">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-350">보기 권한자가 받은 들어오는 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-352">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-353">보기 권한자가 받은 들어오는 타일 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-355">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-356">보기 권한자가 받은 들어오는 타일 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-358">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-359">보기 권한자가 받은 들어오는 타일 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-361">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-362">보기 권한자가 받은 총 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-364">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-365">보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-367">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-368">보기 권한자가 받은 최대 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-370">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-371">보기 권한자가 받은 들어오는 프레임 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-373">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-374">보기 권한자가 받은 들어오는 프레임 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-376">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-377">보기 권한자가 받은 들어오는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-379">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-380">보기 권한자가 받은 들어오는 프레임 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-382">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-383">보기 권한자가 받은 들어오는 프레임 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-385">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-386">보기 권한자가 받은 들어오는 프레임 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-388">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-389">보낸 사람에 대한 총 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-391">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-392">보낸 사람에 대한 평균 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-394">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-395">보낸 사람에 대한 최대 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-397">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-398">보낸 사람에 대한 나가는 타일 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-400">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-401">보낸 사람에 대한 나가는 타일 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-403">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-404">보낸 사람에 대한 나가는 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-406">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-407">보낸 사람에 대한 나가는 타일 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-409">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-410">보낸 사람에 대한 나가는 타일 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-412">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-413">보낸 사람에 대한 나가는 타일 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-415">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-416">보낸 사람에 대한 총 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-418">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-419">보낸 사람에 대한 평균 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-421">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-422">보낸 사람에 대한 최대 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-424">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-425">보낸 사람에 대한 나가는 프레임 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-427">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-428">보낸 사람에 대한 나가는 프레임 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-430">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-431">보낸 사람에 대한 나가는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-433">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-434">보낸 사람에 대한 나가는 프레임 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-436">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-437">보낸 사람에 대한 나가는 프레임 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-439">식</span><span class="sxs-lookup"><span data-stu-id="b7c23-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-440">보낸 사람에 대한 나가는 프레임 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-442">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-443">평균 비디오 해상도 높이(픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-445">int</span><span class="sxs-lookup"><span data-stu-id="b7c23-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-446">평균 비디오 해상도 너비(픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-447"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-448">비트만</span><span class="sxs-lookup"><span data-stu-id="b7c23-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-449">인바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7c23-450"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-451">비트만</span><span class="sxs-lookup"><span data-stu-id="b7c23-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-452">아웃바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7c23-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b7c23-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b7c23-454">비트만</span><span class="sxs-lookup"><span data-stu-id="b7c23-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b7c23-455">1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="b7c23-456">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c23-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

