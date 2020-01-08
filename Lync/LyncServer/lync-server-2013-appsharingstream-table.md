---
title: 'Lync Server 2013: AppSharingStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013의 AppSharingStream 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-21_

AppSharingStream 테이블에는 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭스가 포함 되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.


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
<td><p>Dmtf</p></td>
<td><p>기본, 외래</p></td>
<td><p>세션이 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>동일한 날짜와 동시에 시작 된 세션을 구분 하는 데 사용 되는 순차 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>기본, 외래</p></td>
<td><p>통화에 사용 되는 영상 회선 유형을 나타냅니다. 사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>0 – 오디오</p></li>
<li><p>1-영상 통화</p></li>
<li><p>2-파노라마 비디오</p></li>
<li><p>3-응용 프로그램/데스크톱 공유</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>응용 프로그램 공유 스트림의 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP 패킷 도착 간에 감지 된 평균 지터. (지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP 패킷 도착 사이에서 감지 된 최대 지터. (지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>왕복이</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 평균 시간 (밀리초)입니다. 200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</p>
<p>높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 최대 양 (밀리초)입니다. 200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</p>
<p>높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RTP (실시간 전송 프로토콜) 패킷 손실의 최대 속도입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>전송 된 패킷 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션이 끝날 때 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>응용 프로그램 공유 페이로드에 대 한 설명입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>단방향 총 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>평균 단방향 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>단방향 대기 시간의 최대 양입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>전체 단방향 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>전체 단방향 간격이 발생 합니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 간격 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>전체 단방향 간격 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>응용 프로그램 역할 (공유자 또는 뷰어) 및 콘텐츠 형식.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일에 대해 처리 시간에 걸리는 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일에 대 한 처리 시간 간격</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 밀도 낮은 간격 밀도는 더 나은 시청 환경을 말합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 기간입니다. 짧은 간격 기간은 더 나은 시청 환경과 동등 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처된 타일의 총 속도 (타일/초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처된 타일의 평균 비율 (초당 타일 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처한 타일의 최대 속도 (초 당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>t</p></td>
<td></td>
<td><p>캡처된 타일의 속도 (초 당 타일 단위)의 버스트 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처한 타일 속도의 버스트 밀도 (초당 타일 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처된 타일의 속도 (초당 타일 단위)로 버스트 기간을 유지 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>캡처된 타일의 비율 (초 당 타일 단위) 간격입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처된 타일의 비율 (초당 타일 수)의 간격 밀도</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>캡처된 타일의 비율 (초당 타일 단위) 간격입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 총 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않은 콘텐츠의 평균 백분율이 며, 그 대신 삭제 되 고 새 콘텐츠가 덮어쓰여집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 최대 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 발생</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 밀도.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>표시기에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격이 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지는 않지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 조밀도</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 총 프레임 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 평균 프레임 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 최대 프레임 수를 표시 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 프레임의 버스트 발생</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 프레임의 버스트 밀도.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 프레임의 버스트 지속 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>그래픽 원본에서 프레임의 간격 scraped.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 프레임의 간격 조밀도</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>그래픽 원본에서 scraped 프레임의 간격 지속 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 총 수신 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 수신 프레임의 평균 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 수신 된 최대 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 타일 속도의 버스트 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 타일 속도의 버스트 밀도.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 타일 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Viewer에서 받은 들어오는 타일 속도의 간격 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 타일 속도의 간격 밀도</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 타일 속도의 간격 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 총 수신 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 수신 프레임의 평균 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 최대 수신 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 버스트 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 버스트 밀도.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 간격</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 간격 밀도</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>뷰어에서 받은 들어오는 프레임 속도의 간격 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 총 송신 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 송신 타일 속도의 평균입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 최대 보내는 타일 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대 한 보내는 타일 속도의 버스트 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 송신 타일 속도의 버스트 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 송신 타일 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대 한 보내는 타일 속도의 간격입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 송신 타일 속도의 간격 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 보내는 타일 속도의 간격 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 총 송신 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 평균 송신 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 최대 송신 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대해 보내는 프레임 속도의 버스트 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 보내는 프레임 속도에 대 한 버스트 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람에 대 한 보내는 프레임 속도의 버스트 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보낸 사람에 대해 보내는 프레임 속도의 간격입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 보내는 프레임 속도에 대 한 간격 밀도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보낸 사람의 보내는 프레임 속도에 대 한 간격 기간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>평균 비디오 해상도 높이 (픽셀)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>평균 비디오 해상도 너비 (픽셀 단위)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ipsec</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>인바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>위한</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>아웃 바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>1은 스트림 방향이 호출자에서 피호출자로 되었음을 의미 합니다.</p>
<p>0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

