---
title: 'Lync Server 2013: 미디어 품질 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edeec17bccc4c2084f71d3a052d3a44a34f4ed94
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013의 미디어 품질 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-06-29_

미디어 품질 요약 보고서는 조직에서 통화 품질을 분석하는 데 가장 많이 사용됩니다. 이 보고서는 다음 범주로 세분화된 자세한 QoE(체감 품질) 통화 메트릭을 제공합니다.

  - UC 피어 투 피어 통화 (예: Microsoft Lync 2013 to Microsoft Lync 2013 call)

  - UC 회의 세션

  - PSTN 회의 세션

  - PSTN 통화: 미디어 바이패스

  - PSTN 통화(바이패스 없음): UC 레그

  - PSTN 통화(바이패스 없음): 게이트웨이 레그

  - 기타 통화 유형

보고서를 처음 열면 각 범주에 대한 요약 정보가 표시됩니다. 보고서를 떠나지 않고 각 범주를 확장 하 여 Office Communicator 2007 R2에서 Lync 2013로 수행한 통화와 같은 하위 범주를 확인할 수 있습니다. 그런 다음 이러한 하위 범주로 드릴다운해서 해당 하위 범주 내에서 수행된 각 통화에 대한 세부 정보를 볼 수 있습니다.

Microsoft Lync Server 2013에서는 미디어 품질 요약 보고서에서 데이터를 오디오 통화, 비디오 통화 및 응용 프로그램 공유 통화의 세 가지 통화 유형으로 나눕니다. 각 통화 유형은 보고서에서 고유 섹션으로 표시되며 고유한 사용자 지정 통화 메트릭 집합을 포함합니다.

미디어 품질 요약 보고서에서는 또한 유선 통화와 무선 통화, 내부 통화와 외부 통화, VPN 통화와 비 VPN 통화의 통화 품질 비교를 수행할 수 있도록 필터를 적용할 수도 있습니다.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>미디어 품질 요약 보고서 액세스

미디어 품질 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다. [Lync Server 2013에서](lync-server-2013-call-list-report.md) 다음 메트릭 중 하나를 클릭 하 여 Call List Report로 드릴 다운할 수 있습니다.

  - 통화량

  - 불량 통화율

또한 다음 오디오 통화 메트릭 중 하나를 클릭하여 미디어 품질 메트릭 분포 보고서에 액세스할 수 있습니다.

  - 왕복(밀리초)

  - 저하(MOS)

  - 패킷 손실

  - 지터(밀리초)

  - 힐러 숨김 비율

  - 힐러 늘임 비율

  - 힐러 압축 비율

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 미디어 품질 요약 보고서에서는 액세스 유형(즉, 내부 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결 등의 조건에 따라 반환되는 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.

다음 표에서는 미디어 품질 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="media-quality-summary-report-filters"></a>미디어 품질 요약 보고서 필터

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
<td><p><strong>액세스 유형</strong></p></td>
<td><p>통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>Internal</p></li>
<li><p>외부:</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>유선</p></li>
<li><p>Wireless-n</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 미디어 품질 요약 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>미디어 품질 요약 보고서 메트릭: 오디오 통화 요약

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
<td><p><strong>왕복(밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>저하(MOS)</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중 발생한 MOS(평균 평가점) 저하의 평균 양입니다. 저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다. 값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다. 현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다. Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</p>
<p>정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (ms)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 숨김 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 늘임 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 압축 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>미디어 품질 요약 보고서 메트릭: 비디오 통화 요약

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
<td><p>아웃바운드 패킷에 대한 RTP(실시간 전송 프로토콜) 패킷 손실입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고정 프레임 비율 %</strong></p></td>
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
<td><p>통화 중 클라이언트 장치의 상대적 상태를 나타냅니다.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>미디어 품질 요약 보고서 메트릭: 응용 프로그램 공유 통화 요약

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
<td><p>보기 세션 동안 AS 회의 서버의 평균 RDP 타일 처리 대기 시간입니다. 평균이 높으면 보기 환경의 지연 시간이 길어지고 네트워크 대기 시간이 포함 됩니다. 과부하 회의 서버에서 평균 지연 값이 더욱 높게 나타날 수 있습니다.</p></td>
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

