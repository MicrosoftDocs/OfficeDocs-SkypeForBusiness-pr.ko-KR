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
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013의 미디어 품질 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-06-29_

미디어 품질 요약 보고서는 조직의 통화 품질을 분석할 때 가장 좋은 방법일 수 있습니다 .이 보고서는 다음 범주로 분류 된 자세한 체감 품질 (환경 품질) 통화 메트릭을 제공 합니다.

  - UC 피어 투 피어 통화 (예: Microsoft Lync 2013에서 Microsoft Lync 2013 통화)

  - UC 회의 세션

  - PSTN 회의 세션

  - PSTN 통화: 미디어 바이패스

  - PSTN 통화 (비 바이패스): UC 레그

  - PSTN 통화 (비 바이패스): 게이트웨이 다리

  - 기타 통화 형식

보고서를 처음 열면 이러한 각 범주에 대 한 요약 정보가 표시 됩니다. 보고서를 종료 하지 않고 각 범주를 확장 하 여 Office Communicator 2007 R2에서 Lync 2013로 만든 호출과 같은 하위 범주를 볼 수 있습니다. 그런 다음 하위 범주를 드릴 다운 하 여 해당 범주 내에서 발생 하는 각 통화에 대 한 세부 정보를 확인할 수 있습니다.

Microsoft Lync Server 2013에서 미디어 품질 요약 보고서는 데이터를 음성 통화, 영상 통화, 응용 프로그램 공유 통화 등의 세 가지 통화 유형으로 나눕니다. 각 통화 유형에는 보고서에 고유한 섹션, 그리고 자체 사용자 지정 호출 메트릭 집합이 있습니다.

미디어 품질 요약 보고서를 사용 하면 유선 통화와 무선 통화, 내부 통화, 외부 통화 및 VPN 통화와 비 VPN 통화 간의 통화 음질을 비교할 수 있는 필터를 적용할 수도 있습니다.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>미디어 품질 요약 보고서에 액세스

모니터링 보고서 홈 페이지에서 미디어 품질 요약 보고서에 액세스할 수 있습니다. 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.

  - 통화 볼륨

  - 통화 불량 백분율

또한 다음 오디오 통화 메트릭 중 하나를 클릭 하 여 미디어 품질 메트릭 배포 보고서에 액세스할 수 있습니다.

  - 왕복 (ms)

  - 성능 저하 (SPECIALIST)

  - 패킷 손실

  - 지터 (ms)

  - Healer 숨겨진 비율

  - Healer 늘이기 비율

  - Healer 압축 비율

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 미디어 품질 요약 보고서를 사용 하면 액세스 형식 (즉, 간격 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결을 통해 반환 된 데이터를 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 미디어 품질 요약 보고서에 사용할 수 있는 필터가 나와 있습니다.

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
<td><p><strong>보낸 사람</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>받는 사람</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Access 형식</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>내부용</p></li>
<li><p>내부</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>유</p></li>
<li><p>Wireless-n</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
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

## <a name="metrics"></a>매트릭스

다음 표에는 미디어 품질 요약 보고서에서 제공 하는 정보가 나열 되어 있습니다.

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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>통화 형식/끝점 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다. 통화 유형은 다음과 같습니다.</p>
<ul>
<li><p>UC 피어 투 피어 통화</p></li>
<li><p>UC 회의 세션</p></li>
<li><p>PSTN 회의 세션</p></li>
<li><p>PSTN 통화: 미디어 바이패스</p></li>
<li><p>PSTN 통화 (비 바이패스): UC 레그</p></li>
<li><p>PSTN 통화 (비 바이패스): 게이트웨이 다리</p></li>
<li><p>기타 통화 형식</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 유형별 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 불량 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류 된 총 통화 수입니다. 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (무선 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>무선 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 볼륨 (VPN 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>VPN 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (외부 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>왕복 (ms)</strong></p></td>
<td><p>아니요</p></td>
<td><p>다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다. 100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</p>
<p>많은 라운드트립 값은 국제 통화 라우팅, 라우팅 잘못 구성 또는 오버 로드 된 미디어 서버에 의해 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성능 저하 (SPECIALIST)</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다. 성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다. 0.5 이하의 값은 허용 되는 저하를 나타냅니다. 지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다. Lync server에서 Lync Server는 사용자가 전화를 평가한 방법을 예측 하는 알고리즘 집합을 사용 합니다.</p>
<p>높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다. 품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>지터 (ms)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 도착 간에 감지 된 평균 지터. (지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 숨겨진 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다. (숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 늘이기 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다. (늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 압축 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다. (압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>미디어 품질 요약 보고서 메트릭: 영상 통화 요약

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>통화 형식/끝점 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다. 통화 유형은 다음과 같습니다.</p>
<ul>
<li><p>UC 피어 투 피어 통화</p></li>
<li><p>UC 회의 세션</p></li>
<li><p>PSTN 회의 세션</p></li>
<li><p>PSTN 통화: 미디어 바이패스</p></li>
<li><p>PSTN 통화 (비 바이패스): UC 레그</p></li>
<li><p>PSTN 통화 (비 바이패스): 게이트웨이 다리</p></li>
<li><p>기타 통화 형식</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 유형별 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 불량 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류 된 총 통화 수입니다. 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (무선 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>무선 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 볼륨 (VPN 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>VPN 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (외부 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 비트 전송률 (킬/초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>평균 비디오 비트 전송률 (초당 k b/초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>낮은 비트/속도 비율 (%)</strong></p></td>
<td><p>아니요</p></td>
<td><p>비트 전송률이 낮은 통화의 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃 바운드 패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>아웃 바운드 패킷에 대 한 RTP (리얼 표준시 Transport Protocol) 패킷 손실 (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고정 프레임%</strong></p></td>
<td><p>아니요</p></td>
<td><p>"고정 된" 프레임의 백분율입니다. 고정 프레임에서는 통화의 오디오 부분이 계속 진행 되는 동안 비디오가 중단 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>아웃 바운드 평균 프레임 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중의 아웃 바운드 전송에 대 한 평균 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인바운드 평균 프레임 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중 들어오는 전송에 대 한 평균 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>인바운드 낮은 프레임 속도%</strong></p></td>
<td><p>아니요</p></td>
<td><p>들어오는 비디오의 비트 전송률이 낮은 통화의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>클라이언트 상태%</strong></p></td>
<td></td>
<td><p>통화 중에 클라이언트 장치에 대 한 상대 상태를 나타냅니다.</p></td>
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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>통화 형식/끝점 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다. 통화 유형은 다음과 같습니다.</p>
<ul>
<li><p>UC 피어 투 피어 통화</p></li>
<li><p>UC 회의 세션</p></li>
<li><p>PSTN 회의 세션</p></li>
<li><p>PSTN 통화: 미디어 바이패스</p></li>
<li><p>PSTN 통화 (비 바이패스): UC 레그</p></li>
<li><p>PSTN 통화 (비 바이패스): 게이트웨이 다리</p></li>
<li><p>기타 통화 형식</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 유형별 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 불량 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류 된 총 통화 수입니다. 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (무선 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>무선 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 볼륨 (VPN 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>VPN 연결을 사용한 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 볼륨 (외부 통화)</strong></p></td>
<td><p>아니요</p></td>
<td><p>외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지터 (ms)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 도착 간에 감지 된 평균 지터. (지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>평균 기준 단방향</strong></p></td>
<td><p>아니요</p></td>
<td><p>두 미디어 끝점 사이의 단방향 지연과 평균을 비교한 것입니다. 이것은 단일 홉 대기 시간 측정입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 .RDP 타일 처리 대기 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간입니다. 평균 높음은 보기 환경의 지연 시간을 반영 하 고 네트워크 대기 시간을 포함 합니다. 오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 spoiled 타일 비율 (%)</strong></p></td>
<td><p>아니요</p></td>
<td><p>Spoiled RDP 타일의 총 백분율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

