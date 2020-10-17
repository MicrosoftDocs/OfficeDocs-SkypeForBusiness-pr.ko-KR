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
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513385"
---
# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013의 주요 상태 지표

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-10_

이 문서는 다운로드 센터에서 다운로드할 수 있는 [정상적인 Lync server 포스터를 유지 관리 하는 주요 상태 표시기](https://go.microsoft.com/fwlink/?linkid=391838) 와 함께 제공 됩니다.

![KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터")

이 포스터를 사용 하 여 사용자 환경 문제 노출을 위해 임계값을 갖는 성능 카운터, 키 상태 지표 (KHIs)에 대해 알아볼 수 있습니다. CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.

CQM을 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 게 질문을 제출할 수 있습니다.

포스터는 다음 영역에 대해 설명 합니다.

  - 주요 상태 지표는 무엇입니까?

  - KHI 데이터를 수집 하려면

  - 모든 서버 역할에 대 한 업데이트 관리 흐름

  - 용어

  - 프런트 엔드 서버

  - 백 엔드 SQL 서버

  - 중재 서버

  - 에지 서버

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>주요 상태 지표는 무엇입니까?

주요 상태 표시기는 사용자 환경 문제 노출을 위한 임계값을 갖는 성능 카운터입니다. CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.

KHIs 솔루션이 아닌 표준 Lync 모니터링 솔루션 (예: System Center Operations Manager, 가상 트랜잭션, 모니터링 서버)과 함께 사용 됩니다.

KHI 성능 카운터를 수집 하 고 네트워킹 가이드와 함께 KHI 스프레드시트를 채워서 Lync 배포의 서버 상태를 결정 하는 데 도움이 되는 성과 기록표를 생성 합니다. 채워진 후에는 환경을 복구 하 고 다른 관련자에 대 한 추가 정보를 제공 합니다. 매달 KHIs를 평가 하 고이를 모든 배포의 진행 중인 운영 프로세스에 통합 합니다.

[Lync Server 네트워킹 가이드](https://go.microsoft.com/fwlink/p/?linkid=390677) 를 다운로드 하 여 khis의 전체 목록을 확인 하 고 관련 스프레드시트를 얻을 수 있습니다.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>KHI 데이터를 수집 하려면

1.  각 Lync Server에서 Lync Server 네트워킹 가이드에 포함 된 KHI 스크립트를 실행 합니다. 그러면 성능 모니터 내부에 데이터 수집기가 생성 되 고 이름이 KHI로 나타납니다. 기본적으로 데이터는 15 초 마다 폴링됩니다.

2.  회사 영업일을 시작 하기 전에 각 Lync Server로 이동 하 여 KHI Data 수집기를 시작 합니다.

3.  해당 요일이 끝나면 KHI 데이터 수집기를 중지 하 고 중앙 위치에 데이터를 복사 합니다.

4.  성능 모니터를 사용 하 여 Lync Server 네트워킹 가이드 다운로드에 포함 된 KHI 스프레드시트를 채운 후에는 결과를 권장 대상에 비교 합니다.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>모든 서버 역할에 대 한 업데이트 관리 흐름

Lync 구현의 각 서버에 대해 서버 구성 요소 상태와 시스템 성능이 원하는 수준 이상 인지 확인 하는 것부터 시작 합니다. 그 후에는 전체 Lync 구현에서 서버의 역할과 관련 된 표시기를 확인 해야 합니다.

먼저 모든 서버에 대해 KHI 성능 데이터를 수집 합니다. 각 시스템 역할 (이 문서의 뒷부분에서 설명 하는 세부 정보)에 대해 기본 시스템 구성 요소가 권장 대상을 충족 하는지 확인 합니다. 그렇지 않으면 시스템 성능을 교정 하 고, KHI 데이터를 다시 수집 하 고, 시스템 상태를 확인 한 후에는 Lync 구현에서 서버의 역할에 해당 하는 메트릭을 볼 수 있습니다. 모든 역할에 대 한 구성 요소 상태는 다음과 같이 정의 됩니다.

  - CPU 사용률 \< 80%

  - 평균 디스크 쓰기 \< 10 밀리초

  - 평균 디스크 읽기 \< 10 밀리초

  - 사용 가능한 메모리 \> 20% 시스템 총 MB

  - 네트워크 큐 길이 \< 2

  - 삭제 되는 패킷 (입출력) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>용어

이 포스터에는 다음과 같은 용어와 머리글자어가 사용 됩니다.

MCU = 응용 프로그램 공유 다중 소수점 제어 장치

AV MCU = 오디오/비디오 MCU

IM MCU = 인스턴트 메시징 MCU

C u i = 통합 커뮤니케이션 웹 API

AV에 지 = Edge를 통한 오디오/비디오 통과

AV 인증 = 오디오/비디오 인증

SIP 스택 = Lync의 코어 SIP 구현을 포함 합니다.

데이터 프록시 = edge 회의에 사용 됨

LySS = Lync Storage Service

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>프런트 엔드 서버

다음 권장 되는 KHI는 기본 구성 요소 상태 외에 프런트 엔드 서버와 관련 된 것입니다.


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
<td><p>/AV/IM MCU</p></td>
<td><p>MCU 상태 &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Web Components</p></td>
<td><p>메일 그룹 확장 AD 시간 제한 &lt; 0</p>
<p>ABWQ 실패 = 0</p>
<p>LIS 오류 = 0</p>
<p>인증 오류 &lt; 1/초</p>
<p>거부 된 ASP.NET v4 요청 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 스택</p></td>
<td><p>평균 수신 메시지 처리 &lt; 1 초</p>
<p>들어오는 응답 삭제 &lt; 1/초당 들어오는 요청 &lt; 1/초 손실 됨</p>
<p>큐 대기 시간 &lt; 100 밀리초</p>
<p>프로시저에 대 한 대기 시간 &lt; 100 ms</p>
<p>제한 된 요청 = 0</p>
<p>인증 오류 &lt; 1/초</p>
<p>들어오는 메시지 시간 초과 &lt; 2</p>
<p>평균 받는 메시지 보류 &lt; 1 초</p>
<p>흐름 제어 연결 &lt; 2</p>
<p>평균 출력 큐 지연 &lt; 2 초</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>Storage Service DB 80에서 사용 되는 공간의% &lt;</p>
<p># 복제본 복제 실패 횟수 = 0</p>
<p># 데이터 손실 이벤트의 개수 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>페이지 수명 예상 &gt; 300 초</p>
<p>일괄 처리 요청/초 &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>백 엔드 SQL 서버

다음 권장 되는 KHI는 기본 구성 요소 상태 외에 SQL server에만 해당 됩니다.


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
<td><p>SQL</p></td>
<td><p>페이지 수명 예상 &gt; 300 초</p>
<p>일괄 처리 요청/초 &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>중재 서버

다음 권장 KHI는 기본 구성 요소 상태 외에 중재 서버에만 적용 됩니다.


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
<p>프록시 10로 인 한 실패 한 통화 &lt;</p>
<p>게이트웨이 10으로 인 한 실패 한 통화 &lt;</p>
<p>거부 된 통화 (로그인 또는 아웃) = 0</p>
<p>누락 된 미디어 후보 = 0</p>
<p>미디어 연결 검사 실패 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>에지 서버

다음 권장 KHI는 기본 구성 요소 상태 외에도에 지 서버에만 해당 됩니다.


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
<td><p>잘못 된 요청 &lt; 20/초</p></td>
</tr>
<tr class="even">
<td><p>AV에 지</p></td>
<td><p>인증 실패 &lt; 20/초</p>
<p>할당 실패 &lt; 20/초</p>
<p>패킷 &lt; 300/초 손실 됨</p></td>
</tr>
<tr class="odd">
<td><p>데이터 프록시</p></td>
<td><p>제한 된 서버 연결 &lt; 3</p>
<p>시스템이 조절 &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>SIP 스택</p></td>
<td><p>제한을 초과 하는 연결 삭제 &lt; 1</p>
<p>전송 시간 초과 &lt; 10</p>
<p>흐름 제어 연결 &lt; 100</p>
<p>들어오는 요청 &lt; 1/초 손실</p>
<p>평균 메시지 처리 &lt; 3 초</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 네트워킹 가이드](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[주요 상태 지표: 정상 Lync Server를 유지 관리 하기 위한 기본 사항](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 통화 품질 방법론](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

