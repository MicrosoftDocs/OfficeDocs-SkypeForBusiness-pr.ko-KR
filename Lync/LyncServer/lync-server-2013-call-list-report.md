---
title: 'Lync Server 2013: 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013의 통화 목록 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

통화 목록 보고서는 조직에서 생성 하 고 받은 개별 통화에 대 한 경력 (체감 품질) 메트릭을 제공 합니다. 보고 되는 실제 메트릭은 통화 목록 보고서에 액세스 하는 방법에 따라 달라 집니다. 예를 들어 [Lync Server 2013에서 장치 보고서](lync-server-2013-device-report.md)의 보고서를 열면 장치 보고서에도 보고 되는 다음과 같은 메트릭이 표시 됩니다.

  - 발신자의 마이크

  - 발신자의 강연자

  - 피호출자의 마이크

  - 피호출자의 강연자

  - 음성 전환 시간 비율

그러나 [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md)에서 통화 목록 보고서를 열면 이러한 메트릭이 표시 되지 않습니다. 대신 다음과 같은 메트릭이 표시 됩니다.

  - 왕복 (ms)

  - 성능 저하 (SPECIALIST)

  - 패킷 손실

  - 지터 (ms)

위치 보고서에 보고 되는 메트릭입니다. 그러나 통화 목록 보고서에서 언제 든 지 Detail metric을 클릭 하 여 모든 통화에 대 한 완전 한 체감 품질 정보를 제공할 수 있습니다.

<div>

## <a name="accessing-the-call-list-report"></a>통화 목록 보고서에 액세스

통화 목록 보고서는 다음 보고서에서 액세스할 수 있습니다.

  - [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)

  - [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)

  - [Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)

  - [Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)

통화 목록 보고서 내에서 세부 정보 메트릭을 클릭 하 여 [Lync Server 2013의 통화 정보 보고서](lync-server-2013-call-detail-report.md) 에 액세스할 수 있습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>통화 목록 보고서를 최대한 활용 하기

일부 통화 목록 보고서 메트릭 (예: 음성 전환 시간)이 실제로 측정 되는지 여부를 잊어버린 경우에는 미터법 레이블 위에 마우스를 놓습니다. 그런 다음 메트릭에 대 한 간략 한 설명을 제공 하는 도구 설명이 표시 됩니다.

</div>

<div>

## <a name="filters"></a>필터가

없음. 통화 목록 보고서는 필터링 할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 각 통화에 대 한 통화 목록 보고서에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="call-list-report-metrics"></a>통화 목록 보고서 메트릭

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
<td><p><strong>세부적인</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에 통화에 대 한 추가 정보가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>호출인</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 시작한 사람의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>피호출자</strong></p></td>
<td><p>예</p></td>
<td><p>호출 된 사람의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시작 시간</strong></p></td>
<td><p>예</p></td>
<td><p>통화가 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>종료 시간</strong></p></td>
<td><p>예</p></td>
<td><p>통화가 종료 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 시작한 사람의 끝점에서 사용 하는 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>호출 수신자 사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>호출 된 사람의 끝점에 사용 되는 소프트웨어입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복 (ms)</strong></p></td>
<td><p>예</p></td>
<td><p>다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다. 100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</p>
<p>많은 라운드트립 값은 국제 통화 라우팅, 라우팅 잘못 구성 또는 오버 로드 된 미디어 서버에 의해 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>성능 저하 (SPECIALIST)</strong></p></td>
<td><p>예</p></td>
<td><p>통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다. 성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다. 0.5 이하의 값은 허용 되는 저하를 나타냅니다. 지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다. Lync server에서 Lync Server는 사용자가 전화를 평가한 방법을 예측 하는 알고리즘 집합을 사용 합니다.</p>
<p>높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다. 품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지터</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷 도착 간에 감지 된 평균 지터. (지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 숨겨진 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다. (숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 늘이기 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다. (늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 압축 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다. (압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>연결성</strong></p></td>
<td><p>예</p></td>
<td><p>무선 통신 링크의 유형입니다. 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>오픈</p></li>
<li><p>Dm</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

