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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499505"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="e17ae-102">Lync Server 2013의 AppSharingStream 테이블</span><span class="sxs-lookup"><span data-stu-id="e17ae-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e17ae-103">_**마지막으로 수정 된 항목:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="e17ae-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="e17ae-104">AppSharingStream 테이블은 응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e17ae-105">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e17ae-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e17ae-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e17ae-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e17ae-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="e17ae-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="e17ae-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e17ae-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e17ae-113">세션이 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-115">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-115">int</span></span></p></td>
<td><p><span data-ttu-id="e17ae-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e17ae-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e17ae-117">같은 날짜와 시간에 시작된 세션을 구분하는 데 사용되는 순차 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e17ae-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e17ae-120">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e17ae-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e17ae-p102">통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e17ae-123">0-오디오</span><span class="sxs-lookup"><span data-stu-id="e17ae-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="e17ae-124">1-비디오</span><span class="sxs-lookup"><span data-stu-id="e17ae-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="e17ae-125">2 -- 파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="e17ae-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="e17ae-126">3-응용 프로그램/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="e17ae-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-128">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-128">int</span></span></p></td>
<td><p><span data-ttu-id="e17ae-129">Primary</span><span class="sxs-lookup"><span data-stu-id="e17ae-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="e17ae-130">응용 프로그램 공유 스트림의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-132">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-133">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e17ae-134">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-136">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-137">RTP 패킷 도착 시간 사이에 발견된 최대 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e17ae-138">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-139"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-140">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p105">RTP(Real-time Transport Protocol) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e17ae-p106">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-146">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p107">실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 최대 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e17ae-p108">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-152">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p109">RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-157">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p110">RTP(Real-time Transport Protocol) 패킷 손실의 최대 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-162">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-163">보낸 패킷의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-165">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p111">세션 종료 시 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-169">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-170">응용 프로그램 공유 페이로드의 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-172">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p112">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-176">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p113">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-180">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p114">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-184">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p115">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-189">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p116">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-194">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p117">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-199">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p118">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-204">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p119">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-209">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p120">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="e17ae-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-215">응용 프로그램 역할(공유자 또는 보기 권한자) 및 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-217">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p121">RDP(원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-221">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p122">RDP(원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-225">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p123">RDP(원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-229">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p124">RDP(원격 데스크톱 프로토콜) 타일의 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-233">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p125">RDP(원격 데스크톱 프로토콜) 타일의 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-237">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p126">RDP(원격 데스크톱 프로토콜) 타일의 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-241">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-242">RDP(원격 데스크톱 프로토콜) 타일의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-244">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p127">RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 밀도입니다. 갭 밀도가 낮으면 보기 환경 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-248">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-p128">RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 기간입니다. 갭 기간이 짧으면 보기 환경 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-252">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-253">캡처된 타일의 총 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-255">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-256">캡처된 타일의 평균 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-258">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-259">캡처된 타일의 최대 속도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-261">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-262">캡처된 타일 속도의 버스트 발생 수(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-264">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-265">캡처된 타일 속도의 버스트 밀도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-267">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-268">캡처된 타일 속도의 버스트 기간(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-270">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-271">캡처된 타일 속도의 갭 발생 수(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-273">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-274">캡처된 타일 속도의 갭 밀도(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-276">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-277">캡처된 타일 속도의 갭 기간(초당 타일 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-279">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-280">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 총 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-282">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-283">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-285">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-286">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 최대 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-288">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-289">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-291">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-292">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-294">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-295">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-297">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-298">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-300">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-301">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-303">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-304">보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-306">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-307">그래픽 원본에서 스크랩된 총 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-309">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-310">그래픽 원본에서 스크랩된 평균 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-312">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-313">그래픽 원본에서 스크랩된 최대 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-315">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-316">그래픽 원본에서 스크랩된 프레임의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-318">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-319">그래픽 원본에서 스크랩된 프레임의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-321">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-322">그래픽 원본에서 스크랩된 프레임의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-324">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-325">그래픽 원본에서 스크랩된 프레임의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-327">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-328">그래픽 원본에서 스크랩된 프레임의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-330">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-331">그래픽 원본에서 스크랩된 프레임의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-333">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-334">보기 권한자가 받은 총 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-336">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-337">보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-339">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-340">보기 권한자가 받은 최대 들어오는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-342">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-343">보기 권한자가 받은 들어오는 타일 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-345">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-346">보기 권한자가 받은 들어오는 타일 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-348">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-349">보기 권한자가 받은 들어오는 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-351">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-352">보기 권한자가 받은 들어오는 타일 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-354">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-355">보기 권한자가 받은 들어오는 타일 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-357">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-358">보기 권한자가 받은 들어오는 타일 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-360">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-361">보기 권한자가 받은 총 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-363">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-364">보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-366">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-367">보기 권한자가 받은 최대 들어오는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-369">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-370">보기 권한자가 받은 들어오는 프레임 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-372">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-373">보기 권한자가 받은 들어오는 프레임 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-375">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-376">보기 권한자가 받은 들어오는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-378">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-379">보기 권한자가 받은 들어오는 프레임 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-381">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-382">보기 권한자가 받은 들어오는 프레임 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-384">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-385">보기 권한자가 받은 들어오는 프레임 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-387">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-388">보낸 사람에 대한 총 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-390">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-391">보낸 사람에 대한 평균 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-393">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-394">보낸 사람에 대한 최대 나가는 타일 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-396">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-397">보낸 사람에 대한 나가는 타일 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-399">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-400">보낸 사람에 대한 나가는 타일 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-402">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-403">보낸 사람에 대한 나가는 타일 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-405">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-406">보낸 사람에 대한 나가는 타일 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-408">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-409">보낸 사람에 대한 나가는 타일 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-411">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-412">보낸 사람에 대한 나가는 타일 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-414">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-415">보낸 사람에 대한 총 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-417">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-418">보낸 사람에 대한 평균 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-420">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-421">보낸 사람에 대한 최대 나가는 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-423">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-424">보낸 사람에 대한 나가는 프레임 속도의 버스트 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-426">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-427">보낸 사람에 대한 나가는 프레임 속도의 버스트 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-429">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-430">보낸 사람에 대한 나가는 프레임 속도의 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-432">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-433">보낸 사람에 대한 나가는 프레임 속도의 갭 발생 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-435">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-436">보낸 사람에 대한 나가는 프레임 속도의 갭 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-438">식</span><span class="sxs-lookup"><span data-stu-id="e17ae-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-439">보낸 사람에 대한 나가는 프레임 속도의 갭 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-441">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-442">평균 비디오 해상도 높이(픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-444">int</span><span class="sxs-lookup"><span data-stu-id="e17ae-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-445">평균 비디오 해상도 너비(픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-446"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-447">비트만</span><span class="sxs-lookup"><span data-stu-id="e17ae-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-448">인바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e17ae-449"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-450">비트만</span><span class="sxs-lookup"><span data-stu-id="e17ae-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-451">아웃바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e17ae-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e17ae-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e17ae-453">비트만</span><span class="sxs-lookup"><span data-stu-id="e17ae-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e17ae-454">1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="e17ae-455">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e17ae-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

