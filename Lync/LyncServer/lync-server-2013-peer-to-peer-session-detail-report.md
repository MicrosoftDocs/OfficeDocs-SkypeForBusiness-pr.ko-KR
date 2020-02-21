---
title: 'Lync Server 2013: 피어 투 피어 세션 세부 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe04005d616a97a1fff4c84dbe43a5edb8e3cdba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 세션 정보 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-06_

피어 투 피어 세션 정보 보고서는 피어 투 피어 세션에 대 한 자세한 정보를 반환 합니다. 예를 들어 인스턴트 메시징 세션을 선택 하는 경우 보고서는 세션의 두 사용자가 보낸 메시지 수를 알려줍니다.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>피어 투 피어 세션 세부 정보 보고서 액세스

피어 투 피어 세션 세부 정보 보고서는 다음 보고서에서 액세스할 수 있습니다 (모두 모니터링 보고서 홈 페이지에서 액세스할 수 있음).

  - IP 전화 인벤토리 보고서

  - 사용자 작업 보고서

  - 통화 허용 제어 보고서

  - 오류 목록 보고서

피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013의 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다. 다음 두 메트릭 중 하나를 클릭 하 여 상위 오류 보고서에 액세스할 수도 있습니다.

  - 응답

  - 진단 ID

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>피어 투 피어 세션 세부 정보 보고서를 가장 효율적으로 활용

피어 투 피어 세션 정보 보고서에는 많은 수의 메트릭이 포함 되어 있는데,이는 대부분 시스템 관리자에 게 익숙한 것이 아닙니다. 그러나 종종 메트릭 레이블 위에 마우스를 놓으면 해당 메트릭에 대 한 간략 한 설명을 제공 하는 도구 설명을 볼 수 있습니다.

지정 된 보고서에 표시 되는 실제 메트릭은 선택한 피어 투 피어 세션 유형에 따라 달라 집니다. 오디오/비디오 세션에서는 인스턴트 메시징 세션 보다 다양 한 메트릭 집합을 보고 합니다.

또한 응답 코드 및 진단 ID 메트릭 위로 마우스를 가져가면 해당 값에 대 한 설명을 얻을 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터

없음 피어 투 피어 세션 정보 보고서를 필터링 할 수 없습니다.

</div>

<div>

## <a name="session-information-metrics"></a>세션 정보 메트릭

다음 표에서는 각 세션에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="session-information-metrics"></a>세션 정보 메트릭

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
<td><p><strong>풀 FQDN</strong></p></td>
<td><p>세션에 포함 된 등록자 풀 또는에 지 서버의 FQDN (전체 도메인 이름)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>초대 시간</strong></p></td>
<td><p>세션 초대가 원래 전송 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 시간</strong></p></td>
<td><p>초대 수락이 수신 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시작 사용자</strong></p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>출처 사용자 에이전트</strong></p></td>
<td><p>세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 내부 출처</strong></p></td>
<td><p>세션을 시작한 사용자가 내부 네트워크에 로그온 했는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>일반 전화기와 통합 된 사용자</strong></p></td>
<td><p>세션을 시작한 사용자가 사용 하는 끝점이 자신의 데스크톱 전화와 통합 되어 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 우선 순위</strong></p></td>
<td><p>세션에 할당 된 우선 순위입니다. 유효한 우선 순위는 다음과 같습니다. 비 긴급; 보통인 기울여야 및 긴급</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>세션이 실패했을 때 전송된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>프런트 엔드</strong></p></td>
<td><p>전화 회의에 사용 된 프런트 엔드 서버의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>캡처 시간</strong></p></td>
<td><p>세션 정보가 기록 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>종료 시간</strong></p></td>
<td><p>세션이 종료 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>대상 사용자</strong></p></td>
<td><p>세션에 초대된 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 에이전트</strong></p></td>
<td><p>세션에 초대 된 사용자의 끝점에 사용 된 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 내부</strong></p></td>
<td><p>세션에 초대 된 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>일반 전화기와 통합 된 사용자</strong></p></td>
<td><p>세션에 초대 된 사용자가 사용 하는 끝점이 자신의 데스크톱 전화와 통합 되어 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>재시도 되는 세션</strong></p></td>
<td><p>세션이 이전에 실패 한 세션에 대 한 다시 시도 인지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. ID 번호 위에 마우스를 놓으면 해당 ID에 대 한 추가 정보를 볼 수 있습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>형식에 대 한 메트릭

다음 표에서는 각 세션 형식에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-modalities"></a>형식에 대 한 메트릭

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
<td><p><strong>형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에서 사용 되는 형식입니다. IM (인스턴트 메시징) 또는 파일 전송 등이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 메시지</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자가 보낸 메시지 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 메시지</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 참가 하도록 초대 된 사용자가 보낸 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>진단 보고서에 대 한 메트릭

다음 표에서는 각 진단 보고서에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-diagnostic-reports"></a>진단 보고서에 대 한 메트릭

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
<td><p><strong>사항은</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에 세션에 대 한 진단 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보고서가 기록된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>요청이</strong></p></td>
<td><p>아니요</p></td>
<td><p>SIP 요청 유형입니다. 예: INVITE 또는 BYE</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>콘텐츠 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의에서 사용 되는 미디어 콘텐츠 유형입니다. 예를 들어 공통 콘텐츠 형식은 Application/sdp입니다. SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고 한 사람</strong></p></td>
<td><p>아니요</p></td>
<td><p>문제를 보고 한 컴퓨터 (즉, 클라이언트 또는 서버)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

