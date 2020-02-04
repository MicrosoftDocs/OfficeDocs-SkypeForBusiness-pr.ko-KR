---
title: 'Lync Server 2013: 미디어 품질 비교 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013의 미디어 품질 비교 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-22_

미디어 품질 비교 보고서를 사용 하면 다양 한 종류의 오디오 통화 (예: 무선 네트워크 또는 유선 연결을 통해 생성 된 통화)에 대 한 통화 품질 값을 비교할 수 있습니다.

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>미디어 품질 비교 보고서에 액세스

미디어 품질 비교 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 미디어 품질 비교 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="media-quality-comparison-report-filters"></a>미디어 품질 비교 보고서 필터

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
<td><p><strong>전화가</strong></p></td>
<td><p>주 비교 항목으로 사용할 통화 유형입니다. 사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>내부</p></li>
<li><p>내부용</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
<li><p>유</p></li>
<li><p>Wireless-n</p></li>
<li><p>외장 및 유선</p></li>
<li><p>외부 및 무선</p></li>
<li><p>외부 및 VPN</p></li>
<li><p>외부 및 비 VPN</p></li>
<li><p>내부 및 유선</p></li>
<li><p>내부 및 무선</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>통화와 비교</strong></p></td>
<td><p>보조 비교 항목으로 사용할 통화 유형입니다. 사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>내부</p></li>
<li><p>내부용</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
<li><p>유</p></li>
<li><p>Wireless-n</p></li>
<li><p>외장 및 유선</p></li>
<li><p>외부 및 무선</p></li>
<li><p>외부 및 VPN</p></li>
<li><p>외부 및 비 VPN</p></li>
<li><p>내부 및 유선</p></li>
<li><p>내부 및 무선</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>간격만</strong></p></td>
<td><p>시간 간격. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>매시간 (최대 25 시간 표시할 수 있음)</p></li>
<li><p>매일 (최대 31 일이 표시 될 수 있음)</p></li>
<li><p>주간 (최대 12 주를 표시할 수 있음)</p></li>
</ul>
<p>시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다. 예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 미디어 품질 비교 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="media-quality-comparison-report-metrics"></a>미디어 품질 비교 보고서 메트릭

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
<td><p><strong>통화 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성능 저하 (SPECIALIST)</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중에 발생 한 평균 SPECIALIST (평균 의견 성과)의 감소 금액입니다. 성능 저하 값의 범위는 0.0 ~ 5.0 ~ 높음이 하입니다. 0.5 이하의 값은 허용 되는 저하를 나타냅니다. 지금까지 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 평균 성적 점수가 계산 되었습니다. Lync Server는 사용자가 통화를 평가 하는 방법을 예측 하는 알고리즘 집합을 사용 합니다.</p>
<p>높은 성능 저하 값은 정체로 인해 발생할 수 있습니다. 대역폭 부족, 무선 혼잡 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점. 품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 불량 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류 된 총 통화 수입니다. 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복 (ms)</strong></p></td>
<td><p>아니요</p></td>
<td><p>실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 평균 시간 (밀리초)입니다. 200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</p>
<p>높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

