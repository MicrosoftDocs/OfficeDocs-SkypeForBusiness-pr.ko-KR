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
# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013의 AppSharingStream 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-21_

AppSharingStream 테이블은 응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 포함합니다. 이 표는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p>dateTime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션이 시작된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>같은 날짜와 시간에 시작된 세션을 구분하는 데 사용되는 순차 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>0-오디오</p></li>
<li><p>1-비디오</p></li>
<li><p>2 -- 파노라마 비디오</p></li>
<li><p>3-응용 프로그램/데스크톱 공유</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>응용 프로그램 공유 스트림의 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 최대 지터입니다. (지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>왕복</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP(Real-time Transport Protocol) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 최대 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RTP(Real-time Transport Protocol) 패킷 손실의 최대 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 패킷의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션 종료 시 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>응용 프로그램 공유 페이로드의 설명입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>응용 프로그램 역할(공유자 또는 보기 권한자) 및 콘텐츠 형식입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 갭 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 밀도입니다. 갭 밀도가 낮으면 보기 환경 성능이 향상됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 기간입니다. 갭 기간이 짧으면 보기 환경 성능이 향상됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일의 총 속도(초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일의 평균 속도(초당 타일 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일의 최대 속도(초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>캡처된 타일 속도의 버스트 발생 수(초당 타일 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일 속도의 버스트 밀도(초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일 속도의 버스트 기간(초당 타일 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>캡처된 타일 속도의 갭 발생 수(초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일 속도의 갭 밀도(초당 타일 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>캡처된 타일 속도의 갭 기간(초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 총 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 평균 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 최대 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 총 프레임 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 평균 프레임 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 최대 프레임 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 버스트 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 버스트 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 버스트 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 갭 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 갭 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>그래픽 원본에서 스크랩된 프레임의 갭 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 총 들어오는 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 최대 들어오는 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 버스트 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 버스트 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 갭 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 갭 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 타일 속도의 갭 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 총 들어오는 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 평균 들어오는 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 최대 들어오는 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 버스트 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 버스트 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 갭 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 갭 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보기 권한자가 받은 들어오는 프레임 속도의 갭 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 총 나가는 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 평균 나가는 타일 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 최대 나가는 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 버스트 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 버스트 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 갭 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 갭 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 타일 속도의 갭 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 총 나가는 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 평균 나가는 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 최대 나가는 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 버스트 발생 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 버스트 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 갭 발생 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 갭 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>보낸 사람에 대한 나가는 프레임 속도의 갭 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>평균 비디오 해상도 높이(픽셀)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>평균 비디오 해상도 너비(픽셀)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인바운드</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>인바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃 바운드</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>아웃바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</p>
<p>0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

