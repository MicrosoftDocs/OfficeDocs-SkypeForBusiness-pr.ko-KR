---
title: 'Lync Server 2013: AudioStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013의 AudioStream 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

각 레코드는 하나의 오디오 스트림을 나타냅니다. 일반적으로 하나의 오디오 미디어 선에는 두 개의 오디오 스트림이 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>열</strong></th>
<th><strong>데이터 형식</strong></th>
<th><strong>키/인덱스</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>미디어 라인 내의 고유 ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>통화 중 최대 네트워크 지터.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p> </p></td>
<td><p>통화 중의 평균 패킷 손실 율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p> </p></td>
<td><p>통화 중에 최대 패킷 손실이 관찰 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p> </p></td>
<td><p>통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p> </p></td>
<td><p>패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>패킷 손실의 버스트 간 평균 간격 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>오디오 스트림의 패킷 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>오디오 스트림의 대역폭을 예측 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다. 범위는 0.0 ~ 5.0입니다. 이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다. 허용 되는 품질은 0.5 미만 이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>지터로 인해 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>PayloadDescription 테이블에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>오디오 스트림의 샘플링 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>왕복이</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 통계에서 왕복 시간을 계산 합니다. 적절 한 품질을 위해서는 100ms 보다 작아야 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>오디오 스트림의 최대 라운드트립 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>통화에 대 한 평균 광대역 네트워크 SPECIALIST. 이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다. 범위는 [1.0에서 5.0]입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>통화에 대 한 최소 광대역 네트워크 SPECIALIST.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 발송 된 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>통화에 대 한 최소 SendListenMOS입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p> </p></td>
<td><p>통화에 대 한 최소 RecvListenMOS입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>오디오 및 사용</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>오디오 FEC 통화에 사용 되었는지 여부를 나타내는 플래그입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ipsec</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>수신기 쪽에 있는 스트림 데이터를 수신 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>위한</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>보낸 사람 측에 있는 스트림 데이터를 수신 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다.</p>
<p>0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>지터 도착 시간에 대 한 표준 편차입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Healer에서 숨겨진 패킷의 최대 비율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Healer에서 숨겨진 패킷의 비율에 대 한 표준 편차입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Healer에서 손실 된 패킷의 총 수를 수신 하 여 받은 패킷의 총량을 말합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>받은 총 패킷 수와 비교 하 여 사용한 착신 전환 오류 수정 패킷의 비율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Healer에서 압축 한 최대 오디오 패킷 수입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>네트워크 패킷의 지연 도착으로 인해 혼잡이 있는 통화의 백분율을 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>통화가 네트워크 리소스에 대해 경쟁 하는 시간의 백분율을 나타냅니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 되는 최소 대역폭 예상 양입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중에 측정 되는 최대 대역폭 예상 금액입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중에 측정 되는 대역폭 예상의 표준 편차입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 되는 평균 대역폭 예상 금액입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>단방향 총 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>평균 단방향 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>단방향 대기 시간의 최대 양입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>전체 단방향 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>전체 단방향 간격이 발생 합니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 간격 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 간격 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>스테레오로 디코딩된 통화의 백분율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>음향 반향 제거 기 스테레오로 렌더링 되는 통화의 백분율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>오디오 및이 어//또는 r</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전달 오류 수정 후 패킷 손실 율이 적용 되었습니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>스테레오로 인코딩된 통화의 백분율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>음향 반향 제거 기 스테레오로 캡처한 통화의 백분율입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

