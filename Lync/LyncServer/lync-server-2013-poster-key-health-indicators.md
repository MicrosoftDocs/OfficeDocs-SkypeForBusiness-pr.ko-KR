---
title: 'Lync Server 2013: 포스터: 주요 상태 표시기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013의 주요 상태 표시기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-10_

이 문서는 다운로드 센터에서 다운로드할 수 있는 [정상적인 Lync server 포스터를 유지 관리 하는 주요 상태 표시기](http://go.microsoft.com/fwlink/?linkid=391838) 와 함께 제공 됩니다.

![KHI 데이터를 사용하는 문제 해결에 대해 설명하는 포스터](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI 데이터를 사용하는 문제 해결에 대해 설명하는 포스터")

이 포스터를 사용 하 여 키 상태 표시기 (KHIs), 사용자 환경 문제 발생을 목표로 하는 임계값을 갖는 성능 카운터에 대해 알아볼 수 있습니다. KHI 데이터 수집은 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 초점을 맞춘 CQM (통화 품질 방법론)를 구현 하기 위한 첫 번째 단계입니다.

CQM를 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 질문을 제출할 수 있습니다.

포스터는 다음 영역에 대해 설명 합니다.

  - 주요 상태 지표는 무엇 인가요?

  - KHI 데이터 수집

  - 모든 서버 역할의 업데이트 관리 흐름

  - 용어가

  - 프런트 엔드 서버

  - 백 엔드 SQL Server

  - 중재 서버

  - Edge 서버

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>주요 상태 지표는 무엇 인가요?

주요 상태 표시기는 사용자 환경 문제 노출을 목표로 하는 임계값을 갖는 성능 카운터입니다. KHI 데이터 수집은 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 초점을 맞춘 CQM (통화 품질 방법론)를 구현 하기 위한 첫 번째 단계입니다.

KHIs는 표준 Lync 모니터링 솔루션 (예: System Center Operations Manager, 종합 트랜잭션, 모니터링 서버) 외에는 이러한 솔루션 대신 사용 됩니다.

KHI 성능 카운터를 수집 하 고 네트워크 가이드와 함께 KHI 스프레드시트를 채워 Lync 배포의 서버 상태를 확인 하는 데 도움이 되는 성과 기록표를 만듭니다. 채워진 후에는 환경을 복구 하는 과정을 안내 하 고 다른 관련자에 대 한 추가적인 통찰력을 제공 합니다. 월 단위로 KHIs를 평가 하 고 모든 배포의 진행 중인 운영 프로세스에 통합 합니다.

[Lync Server 네트워킹 가이드](http://go.microsoft.com/fwlink/p/?linkid=390677) 를 다운로드 하 여 모든 khis의 전체 목록을 확인 하 고 관련 스프레드시트를 얻을 수 있습니다.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>KHI 데이터 수집

1.  각 Lync Server의 Lync Server 네트워킹 가이드에 포함 된 KHI 스크립트를 실행 합니다. 이렇게 하면 성능 모니터 내부에 데이터 수집기가 생성 되 고 KHI의 이름을 가집니다. 기본적으로 데이터는 15 초 마다 폴링됩니다.

2.  회사의 영업일 시작 전에 각 Lync 서버로 이동 하 여 KHI 데이터 수집기를 시작 합니다.

3.  이 날이 끝날 때 KHI 데이터 수집기를 중지 하 고 데이터를 중앙 위치에 복사 합니다.

4.  성능 모니터를 사용 하 여 Lync Server 네트워킹 가이드 다운로드에 포함 된 KHI 스프레드시트를 입력 한 후 추천 대상과 결과를 비교 합니다.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>모든 서버 역할의 업데이트 관리 흐름

Lync 구현의 각 서버에 대해 서버의 구성 요소 상태와 시스템 성능이 원하는 수준 이상 인지 확인 하는 것부터 시작 합니다. 그 이후에는 전체 Lync 구현에서 서버의 역할과 관련 된 표시기를 확인 해야 합니다.

먼저 모든 서버에 대 한 KHI 성능 데이터를 수집 합니다. 각 시스템 역할 (이 문서의 뒷부분에 설명 된 세부 정보)에 대해 기본 시스템 구성 요소가 권장 대상에 맞는지 여부를 확인 합니다. 그렇지 않은 경우 시스템 성능을 재구성 한 다음 KHI 데이터를 다시 수집 하 고 Lync 구현에서 서버의 역할에 대 한 메트릭을 확인 하기 전에 시스템 상태를 유지 합니다. 모든 역할의 구성 요소 상태는 다음과 같이 정의 됩니다.

  - CPU 이용률 \< 80%

  - 평균 디스크 쓰기 \< 10 밀리초

  - 평균 디스크 읽기 \< 10 밀리초

  - 사용 가능한 \>메모리 20% 시스템 총 MB

  - 네트워크 대기열 길이 \< 2

  - 버림 패킷 (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>용어가

이 포스터에 사용 되는 용어와 머리글자어는 다음과 같습니다.

MCU = Application 공유 다중 소수점 제어 단위

AV MCU = 오디오/비디오 MCU

IM MCU = 인스턴트 메시지 MCU

통합 커뮤니케이션 웹 API

AV 가장자리 = Edge를 통한 오디오/비디오의 트래버스

AV 인증 = 오디오/비디오 인증

SIP 스택 = Lync의 코어 SIP 구현을 포함 합니다.

데이터 프록시 = edge 회의에 사용 됨

LySS = Lync 저장소 서비스

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>프런트 엔드 서버

다음과 같은 권장 KHI는 기본 구성 요소 상태 외에도 프런트 엔드 서버에만 해당 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능 영역</th>
<th>대상 메트릭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/메신저 MCU</p></td>
<td><p>MCU 상태 &lt;2</p></td>
</tr>
<tr class="even">
<td><p>웹 구성 요소</p></td>
<td><p>메일 그룹 확장 광고 시간 &lt;제한 0</p>
<p>ABWQ 오류 = 0</p>
<p>LIS 오류 = 0</p>
<p>인증 오류 &lt; 1/초</p>
<p>ASP.NET v4 요청이 거부 됨 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 스택</p></td>
<td><p>평균 수신 메시지 처리 &lt; 1 초</p>
<p>수신 응답 손실 &lt; 됨 1/초 수신 요청이 &lt; 1 초/초로 삭제 됨</p>
<p>대기열 지연 &lt; 100 ms</p>
<p>프로시저를 &lt; 통해 대기 시간 100 ms</p>
<p>제한 되는 요청 = 0</p>
<p>인증 오류 &lt; 1/초</p>
<p>받는 메시지가 시간 초과 &lt; 됨 2</p>
<p>평균 수신 메시지 대기 &lt; 1 초</p>
<p>흐름 제어 연결 &lt; 2</p>
<p>평균 아웃 대기열 지연 &lt; 2 초</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>저장소 서비스 DB &lt; 80에서 사용 된 공간의%</p>
<p>#복제 복제 실패 횟수 = 0</p>
<p>#데이터 손실 이벤트의 개수 = 0</p></td>
</tr>
<tr class="odd">
<td><p>TEST.SQL</p></td>
<td><p>페이지 수명 예상 &gt; 300 초입니다.</p>
<p>일괄 처리 요청/ &lt; 초 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>백 엔드 SQL Server

다음과 같은 권장 KHI는 기본 구성 요소 상태 외에 SQL server에만 해당 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능 영역</th>
<th>대상 메트릭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TEST.SQL</p></td>
<td><p>페이지 수명 예상 &gt; 300 초입니다.</p>
<p>일괄 처리 요청/ &lt; 초 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>중재 서버

다음과 같은 권장 KHI는 기본 구성 요소 상태 외에 중재 서버에만 해당 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능 영역</th>
<th>대상 메트릭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>중재 서버 서비스</p></td>
<td><p>로드 통화 실패 인덱스 = 0</p>
<p>프록시 &lt;10 때문에 실패 한 통화</p>
<p>게이트웨이 &lt;10으로 인 한 통화 실패</p>
<p>통화 (in 또는 out)가 거부 됨 = 0</p>
<p>미디어 후보자 누락 = 0</p>
<p>미디어 연결 검사 실패 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edge 서버

다음과 같은 권장 KHI는 기본 구성 요소 상태 외에도 edge 서버에만 해당 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능 영역</th>
<th>대상 메트릭</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV 인증</p></td>
<td><p>잘못 된 &lt; 요청 20/초</p></td>
</tr>
<tr class="even">
<td><p>AV 가장자리</p></td>
<td><p>인증. 실패 &lt;20/초</p>
<p>할당 실패 &lt;20/초</p>
<p>패킷 300 &lt;/초 손실 됨</p></td>
</tr>
<tr class="odd">
<td><p>데이터 프록시</p></td>
<td><p>제한 서버 연결 &lt; 3</p>
<p>시스템의 스로틀 &lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP 스택</p></td>
<td><p>연결에 극한이 &lt; 생략 된 경우 1</p>
<p>전송 시간 초과 &lt;10</p>
<p>흐름 제어 연결 &lt;100</p>
<p>수신 요청이 1 &lt; /초로 삭제 됨</p>
<p>평균 메시지 처리 &lt; 3 초</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 네트워킹 가이드](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[주요 상태 표시기: 정상적인 Lync 서버를 유지 관리 하기 위한 토대](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 통화 음질 방법](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

