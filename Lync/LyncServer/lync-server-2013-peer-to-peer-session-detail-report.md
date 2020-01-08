---
title: 'Lync Server 2013: 피어 투 피어 세션 세부 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73febb248a8b61979c0aad2df6977c9feccb91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 세션 세부 정보 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

피어 투 피어 세션 정보 보고서는 피어 투 피어 세션에 대 한 자세한 정보를 반환 합니다. 예를 들어 메신저 대화를 선택 하면 보고서에서 세션의 두 사용자 각각에 게 보낸 메시지 수를 알 수 있습니다.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>피어 투 피어 세션 세부 정보 보고서에 액세스

피어 투 피어 세션 세부 정보 보고서는 다음 보고서 중 하나에서 액세스할 수 있습니다 (모두 모니터링 보고서 홈 페이지에서 액세스할 수 있음).

  - IP 전화 인벤토리 보고서

  - 사용자 활동 보고서

  - 통화 허용 제어 보고서

  - 오류 목록 보고서

피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013에서 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다. 다음 두 가지 메트릭 중 하나를 클릭 하 여 상위 오류 보고서에 액세스할 수도 있습니다.

  - 응답

  - 진단 ID

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>피어 투 피어 세션 세부 정보 보고서를 최대한 활용 하기

피어 투 피어 세션 세부 정보 보고서에는 다 수의 메트릭이 포함 되어 있으며,이 중 상당수는 시스템 관리자에 게 익숙하지 않을 수 있습니다. 그러나 종종 미터법 레이블을 마우스로 눌러 해당 메트릭의 간략 한 설명을 제공 하는 도구 설명을 볼 수 있습니다.

지정 된 보고서에 표시 되는 실제 메트릭은 선택한 피어 투 피어 세션의 유형에 따라 달라 집니다. 오디오/비디오 세션은 인스턴트 메시지 세션 보다 다른 메트릭 집합을 보고 합니다.

이러한 값에 대 한 설명을 얻으려면 응답 코드 및 진단 ID 메트릭스 위에 마우스를 놓고 있어야 할 수도 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

없음. 피어 투 피어 세션 세부 정보 보고서를 필터링 할 수 없습니다.

</div>

<div>

## <a name="session-information-metrics"></a>세션 정보 메트릭

다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.

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
<td><p>세션과 관련 된 등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>초대 시간</strong></p></td>
<td><p>세션 초대를 원래 보낸 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 시간</strong></p></td>
<td><p>초대 수락을 받은 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자의</strong></p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 에이전트에서</strong></p></td>
<td><p>세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자의 내부용입니다.</strong></p></td>
<td><p>세션을 시작한 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>일반 전화기와 통합 된 사용자 인 경우</strong></p></td>
<td><p>세션을 시작한 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 우선 순위</strong></p></td>
<td><p>세션에 할당 된 우선 순위입니다. 유효한 우선 순위: 알 수 없음 비 긴급 크기로 받기 및 비상.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>프론트 엔드</strong></p></td>
<td><p>회의에 사용 되는 프런트 엔드 서버의 이름입니다.</p></td>
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
<td><p><strong>사용자에 게</strong></p></td>
<td><p>세션에 초대 된 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 에이전트에</strong></p></td>
<td><p>세션에 초대 된 사용자의 끝점에서 사용 하는 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 내부용</strong></p></td>
<td><p>세션에 초대 된 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>일반 전화기와 사용자 통합</strong></p></td>
<td><p>세션에 초대 된 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>다시 시도 세션</strong></p></td>
<td><p>세션이 이전에 실패 한 세션을 다시 시도 하려고 하는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다. ID 번호 위에 마우스를 놓으면 해당 ID에 대 한 추가 정보를 볼 수 있습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>형식을에 대 한 메트릭

다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-modalities"></a>형식을에 대 한 메트릭

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
<td><p><strong>형식을</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 사용 되는 형식을. 예를 들어 인스턴트 메시지 (IM) 또는 파일 전송</p></td>
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

다음 표에는 각 진단 보고서에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.

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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>도</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에는 세션에 대 한 진단 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고서 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보고서가 기록 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>요청당</strong></p></td>
<td><p>아니요</p></td>
<td><p>SIP 요청 유형입니다. 예를 들어 초대 또는 BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>콘텐츠 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 사용 되는 미디어 콘텐츠의 유형입니다. 예를 들어 공용 콘텐츠 형식은 Application/sdp입니다. SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고 한 사람</strong></p></td>
<td><p>아니요</p></td>
<td><p>컴퓨터 (즉, 클라이언트 또는 서버)에서 문제를 보고 했습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

