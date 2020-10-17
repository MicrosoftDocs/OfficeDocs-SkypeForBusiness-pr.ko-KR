---
title: 'Lync Server 2013: 통화 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef309873ef51e06903123dfb5a1b6ecf68b4ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502755"
---
# <a name="call-detail-report-in-lync-server-2013"></a>Lync Server 2013의 통화 정보 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

통화 정보 보고서는 개별 통화에 대 한 자세한 정보를 제공 합니다. 이 보고서에는 다음과 같은 보고서 섹션으로 구분 된 Lync Server에서 수집한 거의 모든 품질 메트릭 및 통계가 포함 되어 있습니다.

  - 통화 정보

  - 발신자 장치 및 신호 품질 기준

  - 수신자 장치 및 신호 품질 기준

  - 발신자 클라이언트 이벤트

  - 수신자 클라이언트 이벤트

  - 오디오 스트림(발신자에게서 수신자 방향)

  - 비디오 스트림(발신자에게서 수신자 방향)

  - 오디오 스트림(수신자에게서 발신자 방향)

  - 비디오 스트림(수신자에게서 발신자 방향)

지정된 보고서에 표시되는 범주와 메트릭은 두 가지 항목, 즉 세션의 유형과 해당 세션에서 사용되는 끝점의 유형에 따라 달라집니다. 예를 들어 오디오 전용 통화의 경우 비디오 스트림이 없기 때문에 비디오 스트림에 대한 메트릭이 보고되지 않습니다. 마찬가지로 보고서에 발신자 통계만 표시되고 수신자 통계는 표시되지 않을 수도 있습니다. 이는 일반적으로 수신자가 SIP 호환 장치를 사용하지 않았기 때문입니다. 끝점은 통화 종료 시의 통계를 보고하지만 SIP 또는 SIP 통계를 인식하지 못하는 휴대폰은 이러한 종류의 정보를 보고할 수 없습니다. 전화를 걸어 수신자가 휴대폰에서 전화를 받는 경우에는 통화 종료 시 해당 휴대폰에서 보고서가 제공되지 않습니다.

통화 정보 보고서는 지정된 통화에서 미디어 품질 문제가 발생한 이유를 정확히 확인하려는 경우에 가장 유용합니다.

<div>

## <a name="accessing-the-call-detail-report"></a>통화 정보 보고서 액세스

다음 보고서에서 통화 정보 보고서에 액세스할 수 있습니다.

  - [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - [Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - Lync server [2013에서 통화 목록 보고서](lync-server-2013-call-list-report.md) 를 클릭 하 고 세부 정보 메트릭을 클릭 하 여 온- [2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md)

  - [Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) (세부 정보 메트릭 클릭)

통화 정보 보고서 내에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) 에 액세스할 수 있습니다.

  - 캡처 장치

  - 렌더링 장치

A/V 에지 서버 메트릭을 클릭하면 서버 미디어 품질 추세 보고서에도 액세스할 수 있습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>통화 정보 보고서를 가장 효율적으로 활용

통화 정보 보고서에는 보통 서로 다른 250개의 메트릭이 포함되며, 여기에는 마이크 타임스탬프 드리프트, 낮은 SNR 시간, 수화자 에코 시간 등의 항목이 있습니다. 이러한 모든 메트릭이 실제로 측정하는 항목을 기억하기가 어려우면 메트릭 레이블 위에 마우스를 놓아 보십시오. 그러면 대부분의 경우 해당 메트릭을 설명하는 도구 설명이 나타납니다.

메트릭을 찾기가 어려우면 검색 상자에 메트릭 레이블의 일부분을 입력하고 찾기를 클릭합니다. 예를 들어 낮은 SNR 시간 메트릭을 찾을 수 없는 경우 검색 상자에 SNR을 입력하고 찾기를 클릭합니다.

보고서는 통화에 대 한 정보를 추적 합니다. 통화 자체가 기록 되지 않습니다.

</div>

<div>

## <a name="filters"></a>필터

없음. 통화 정보 보고서는 필터링할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 각 통화에 대해 통화 정보 보고서에 제공된 정보를 보여 줍니다.

### <a name="call-detail-report-metrics"></a>통화 정보 보고서 메트릭

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
<td><p><strong>발신자 PAI</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자의 P-Asserted-Identity입니다. P-Asserted-Identity는 트러스트된 네트워크 내에서 사용자의 입증된 ID를 전달하기 위해 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 URI</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>발신자 끝점</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화에 사용된 장치입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 사용자 에이전트</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 장치에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 시작</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 처음 발생한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>중재 서버 바이패스 통화</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 중재 서버를 거치지 않고 PSTN 음성 게이트웨이 또는 적격한 IP-PBX에 연결되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>발신자 OS</strong></p></td>
<td><p>아니요</p></td>
<td><p>발신자 컴퓨터의 운영 체제입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 CPU</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자 컴퓨터에 설치된 CPU입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>발신자 CPU 코어 수</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자가 사용한 컴퓨터의 프로세서 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 CPU 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자가 사용한 컴퓨터의 CPU 클럭 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>발신자 CPU 가상화</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자가 사용한 컴퓨터에 사용된 가상화(있는 경우)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 PAI</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화에 참가하도록 초대된 사용자의 P-Asserted-Identity입니다. P-Asserted-Identity는 트러스트된 네트워크 내에서 사용자의 입증된 ID를 전달하기 위해 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>수신자 URI</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 끝점</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받기 위해 사용된 장치입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>수신자 사용자 에이전트</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 장치에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>기간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 시간 길이입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>미디어 바이패스 경고 플래그</strong></p></td>
<td><p>아니요</p></td>
<td><p>중재 서버를 바이패스할 때 발생한 경고입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 OS</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자 컴퓨터의 운영 체제입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>수신자 CPU</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자 컴퓨터에 설치된 CPU입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 코어 수</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자가 사용한 컴퓨터의 프로세서 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>수신자 CPU 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자가 사용한 컴퓨터의 CPU 클럭 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 CPU 가상화</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자가 사용한 컴퓨터에 사용된 가상화(있는 경우)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

