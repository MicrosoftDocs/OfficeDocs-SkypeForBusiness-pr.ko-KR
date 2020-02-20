---
title: 'Lync Server 2013: 서버 성능 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Lync Server 2013의 서버 성능 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

서버 성능 보고서는 잘못 된 통화의 최고 비율을 경험한 Microsoft Lync Server 2013 서버 목록을 제공 합니다. 보고서에서는 서버 유형별 서버를 분해 하 고 다음 유형에 대 한 별도의 통계를 보고 합니다.

  - 중재 서버

  - A/V 회의 서버

  - A/V 에지 서버

  - 게이트웨이(중재 서버)

  - 게이트웨이(중재 서버 바이패스)

  - 비디오(A/V 회의 서버 및 A/V 에지 서버에 대한 비디오 메트릭 포함)

  - 응용 프로그램 공유(A/V 회의 서버 및 A/V 에지 서버에 대한 응용 프로그램 공유 메트릭 포함)

이 보고서에 나타나는 순위는 상대적인 순위입니다. 예를 들어 가장 성능이 낮은 서버에서 이루어진 통화 1,000건 중 불량 통화가 1건인 경우 불량 통화율이 0.1%이므로 허용되는 비율보다 높습니다. 그러나 다른 모든 서버의 불량 통화율이 0.1%보다도 더 낮아 이 서버의 성능이 가장 낮게 나온 경우 이 서버가 서버 성능 보고서에 여전히 나타납니다.

<div>

## <a name="accessing-the-server-performance-report"></a>서버 성능 보고서 액세스

서버 성능 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다. [Lync Server 2013에서](lync-server-2013-call-list-report.md) 다음 메트릭 중 하나를 클릭 하 여 Call List Report로 드릴 다운할 수 있습니다.

  - 통화량

  - 불량 통화율

또한 다음 메트릭을 클릭하여 서버 미디어 품질 추세 보고서로 드릴다운할 수 있습니다.

  - 보여줍니다

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>서버 성능 보고서의 효과적인 활용

서버 성능 보고서에서는 여러 방식으로 데이터를 필터링할 수 있습니다. 예를 들어 네트워크 유형(유선 연결에서 수행된 통화와 무선 연결에서 수행된 통화) 및 액세스 유형(방화벽 내부에서 수행된 통화와 방화벽 외부에서 수행된 통화)을 기준으로 데이터를 필터링할 수 있습니다. 서버 성능 보고서를 확인할 때 이러한 필터를 활용하는 것이 좋습니다. 예를 들어 중재 서버의 불량 통화율이 3.24%일 경우 무선 통화만 확인해 보면 같은 서버의 불량 통화율이 20%에 육박할 수 있습니다. 이는 이 서버가 무선 통화에 문제가 있었음을 나타냅니다. 이 서버는 유선 통화에 문제가 없었기 때문에 필터를 활용하지 않았다면 이 문제가 있다는 것을 다소 파악하기 힘들었을 것입니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 서버 성능 보고서에서는 반환된 데이터를 서버 유형 또는 네트워크 유형(즉, 유선 또는 무선)별로 필터링하는 등의 작업을 수행할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 데이터는 시간, 일, 주 또는 월별로 그룹화됩니다.

다음 표에서는 서버 성능 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="server-performance-report-filters"></a>서버 성능 보고서 필터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>서버 유형</strong></p></td>
<td><p>성능을 보고할 서버 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>중재 서버</p></li>
<li><p>A/V 회의 서버</p></li>
<li><p>A/V 에지 서버</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>상위 N</strong></p></td>
<td><p>각 범주에 표시할 서버 수(풀 통화 비율 기반)를 나타냅니다. 예를 들어 <strong>5</strong>를 선택하면 5개의 성능이 가장 낮은 서버가 표시됩니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>2-5</p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>액세스 유형</strong></p></td>
<td><p>통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>Internal</p></li>
<li><p>외부:</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>유선</p></li>
<li><p>Wireless-n</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 서버 성능 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="server-performance-report-metrics-audio-call-summary"></a>서버 성능 보고서 메트릭: 오디오 통화 요약

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>서버</strong></p></td>
<td><p>아니요</p></td>
<td><p>서버의 이름/IP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화량</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행된 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>불량 통화율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복(밀리초)</strong></p></td>
<td><p>예</p></td>
<td><p>RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>저하(MOS)</strong></p></td>
<td><p>예</p></td>
<td><p>통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다. 저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다. 값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다. 현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다. Lync Server에서 모니터링 서버는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</p>
<p>정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>예</p></td>
<td><p>RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지터(밀리초)</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 숨김 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 늘임 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 압축 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>서버 성능 보고서 메트릭: 비디오 통화 요약

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>통화 유형/끝점 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</p>
<ul>
<li><p>UC 피어 투 피어 통화</p></li>
<li><p>UC 회의 세션</p></li>
<li><p>PSTN 회의 세션</p></li>
<li><p>PSTN 통화: 미디어 바이패스</p></li>
<li><p>PSTN 통화(바이패스 없음): UC 레그</p></li>
<li><p>PSTN 통화(바이패스 없음): 게이트웨이 레그</p></li>
<li><p>기타 통화 유형</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화량</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 유형별 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>불량 통화율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</p></td>
</tr>
<tr class="even">
<td><p><strong>통화량(무선 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>무선 연결이 사용된 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화량(VPN 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>VPN 연결이 사용된 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화량(외부 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 비트 전송률(킬로비트/초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>비디오의 평균 비트 전송률(킬로비트/초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>낮은 비트 전송률 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>비트 전송률이 낮은 통화의 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃바운드 패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>아웃바운드 패킷의 RTP(Real-time Transport Protocol) 패킷 손실입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>정지된 프레임 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>정지된 프레임의 비율입니다. 정지된 프레임에서는 통화의 오디오 부분이 계속되는 동안 비디오 진행이 멈춥니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃바운드 평균 프레임 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중 아웃바운드 전송의 평균 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인바운드 평균 프레임 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중 들어오는 전송의 평균 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>인바운드 낮은 프레임 속도 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>수신 비디오의 비트 전송률이 낮은 통화의 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>클라이언트 상태 비율</strong></p></td>
<td></td>
<td><p>통화 시 클라이언트 장치의 상대적인 상태를 나타냅니다.</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>서버 성능 보고서 메트릭: 응용 프로그램 공유 통화 요약

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>통화 유형/끝점 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</p>
<ul>
<li><p>UC 피어 투 피어 통화</p></li>
<li><p>UC 회의 세션</p></li>
<li><p>PSTN 회의 세션</p></li>
<li><p>PSTN 통화: 미디어 바이패스</p></li>
<li><p>PSTN 통화(바이패스 없음): UC 레그</p></li>
<li><p>PSTN 통화(바이패스 없음): 게이트웨이 레그</p></li>
<li><p>기타 통화 유형</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화량</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 유형별 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>불량 통화율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</p></td>
</tr>
<tr class="even">
<td><p><strong>통화량(무선 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>무선 연결이 사용된 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화량(VPN 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>VPN 연결이 사용된 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화량(외부 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</p></td>
</tr>
<tr class="odd">
<td><p><strong>지터(밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>평균 상대 단방향</strong></p></td>
<td><p>아니요</p></td>
<td><p>두 미디어 끝점 간의 평균 상대 단방향 지연입니다. 이는 단일 홉 대기 시간 측정값입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 RDP 타일 처리 대기 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보기 세션 동안 AS 회의 서버의 평균 RDP 타일 처리 대기 시간입니다. 이 메트릭에는 네트워크 대기 시간이 포함되지 않습니다. 평균이 높으면 보기 환경의 지연이 긴 것입니다. 과부하 회의 서버에서 평균 지연 값이 더욱 높게 나타날 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 손상 타일 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>손상된 RDP 타일의 총 비율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

