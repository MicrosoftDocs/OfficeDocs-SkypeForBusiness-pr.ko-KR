---
title: 'Lync Server 2013: VideoStream 테이블'
description: 'Lync Server 2013: VideoStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567994"
---
# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013의 VideoStream 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-12-13_

각 레코드는 하나의 비디오 스트림을 나타냅니다. 일반적으로 하나의 비디오 미디어 회선에는 두 개의 비디오 스트림이 있습니다.


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
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Conferencedatetime이 동일할</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 되는 R</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>미디어 회선 내의 고유 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>외부, 기본</p></td>
<td><p>페이로드 설명입니다. 자세한 내용은 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 세션 중의 최대 네트워크 지터입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 통계로부터의 왕복 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 스트림에 대 한 최대 왕복 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p> </p></td>
<td><p>통화 중 평균 패킷 손실 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p> </p></td>
<td><p>통화 중 관측된 최대 패킷 손실입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 스트림에 대 한 대역폭 예상</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 스트림의 평균 비트 전송률입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p> </p></td>
<td><p>수신 된 비디오 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p> </p></td>
<td><p>전송 된 비디오 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>비디오 세션 중의 최대 비디오 비트 전송률입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p> </p></td>
<td><p>총 비디오 프레임 중 손실 된 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td></td>
<td><p>총 비디오 프레임 중 손실 된 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>CIF (Common 교환 형식) 해상도 인 통화 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>VGA 해상도 인 통화 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>HD720 resolution에 있던 통화의 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>프레임 놓기가 없는 통화 기간 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>B 프레임 놓기가 있는 통화 기간 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BP 프레임 낙하의 통화 시간 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BPSP 프레임 하강 통화 지속 시간 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BPSPI 프레임 하강 통화 기간 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인바운드</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>수신기 쪽의 Stream 데이터를 수신 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃 바운드</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>보낸 사람 쪽의 스트림 데이터가 수신 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</p>
<p>0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>네트워크 패킷의 지연 도착으로 인해 혼잡이 발생 한 통화 비율을 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>호출이 네트워크 리소스를 경합 하는 시간 비율을 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 된 최소 대역폭 예상 크기입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 된 최대 대역폭 예상 크기입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 된 대역폭 예상 범위의 표준 편차입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>통화 중 측정 된 평균 대역폭 양입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>끝점에서 네트워크 연결이 멀티뷰 video를 지원 하지 않는 것으로 확인 된 통화 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td></td>
<td><p>비디오 패킷이 손실된 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>비디오에 할당된 평균 대역폭 양입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>외부</p></td>
<td><p>보낸 사람이 사용 하는 비디오 코덱 유형입니다. 자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람이 사용 하는 해상도 너비입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람이 사용한 해상도 높이입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람이 사용 하는 평균 비디오 프레임 속도 전송입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대 한 최대 비트 전송률입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대 한 평균 비트 전송률입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람이 사용 하는 비디오 스트림의 최대 개수입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>외부</p></td>
<td><p>수신자가 사용 하는 비디오 코드입니다. 자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>수신자가 사용한 해상도 너비입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>수신자가 사용한 해상도 높이입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>수신자가 사용한 비디오 프레임 속도의 평균입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>수신자의 최대 비트 전송률입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>수신자의 평균 비트 전송률입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>받는 사람에 대 한 최대 비디오 스트림입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>받는 사람에 대 한 최소 비디오 스트림입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>수신기의 비디오 모드 (예: 갤러리 또는 단일 스트림)입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>전달 오류 정정이 적용 된 후의 패킷 손실 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>동적 기능 플래그가 활성 상태인 시간 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>통화 중 측정 된 최소 해상도입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>낮은 비트 전송률 임계값에 해당 하는 통화 비율 (초당 70 킬로 비트)입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>낮은 프레임 속도 임계값 (초당 7.5 프레임, 인바운드) 아래의 통화 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>최저 해상도에서 발생 한 통화 비율입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>통화 길이 (초)입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>데이터가 여러 통화 로부터 집계 되었는지 여부를 나타냅니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

