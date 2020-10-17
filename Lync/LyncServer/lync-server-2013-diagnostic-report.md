---
title: 'Lync Server 2013: 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514495"
---
# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 진단 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-07_

진단 보고서에서는 실패한 세션에 대한 진단 및 문제 해결 정보를 제공합니다. 이 정보에는 세션이 실패할 때 보고된 진단 ID와 진단 헤더가 모두 포함됩니다. 진단 ID는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)이며, 진단 헤더는 진단 ID에 대해 함께 표시할 설명을 제공합니다. 또한 이 보고서에는 보고 구성 요소에서 인식된 유용한 문제 해결 정보가 포함될 수 있습니다. 예를 들면 다음과 같습니다.

  - 오류를 일으킨 PSTN 게이트웨이에서 제공되는 이유 코드. PSTN 네트워크에서 발신 전화에 실패하면 ISUP(ISDN User Part) 이유 코드가 자동으로 생성됩니다. 예를 들어 PSTN 게이트웨이에서 전화를 완료하는 데 사용 가능한 회로 또는 채널이 없음을 나타내는 이유 코드 34를 전송할 수 있습니다.

  - 연결 오류를 해결하기 위한 피어 FQDN, 포트 및 Winsock 오류

  - DNS 확인 오류를 해결하기 위한 조회 대상 이름. DNS 확인은 클라이언트가 네임 서버에 연결하여 지정된 장치 이름에 해당하는 IP 주소를 요청할 때마다 수행됩니다.

<div>

## <a name="accessing-the-diagnostic-report"></a>진단 보고서 액세스

[Lync Server 2013의 피어 투 피어 세션 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 또는 전화 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터

없음. 진단 보고서는 필터링할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 각 세션에 대해 진단 보고서에 제공된 정보를 보여 줍니다.

### <a name="diagnostic-report-metrics"></a>진단 보고서 메트릭

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
<td><p><strong>보고 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보고서가 기록된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>응답 코드</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 실패했을 때 전송된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>요청 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 SIP 요청 유형입니다. 예: INVITE, BYE 또는 SERVICE</p></td>
</tr>
<tr class="even">
<td><p><strong>원본</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 원본입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>보낸 사용자 URI</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>출처 사용자 에이전트</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>콘텐츠 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 미디어 콘텐츠 형식입니다. 예를 들어 공통 콘텐츠 형식은 Application/sdp입니다. SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응용 프로그램</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류와 관련된 응용 프로그램입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>대상 사용자 URI</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 초대된 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 회의 참가 시간(밀리초)</p></td>
<td><p>아니요</p></td>
<td><p>사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 헤더</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 ID 설명입니다.</p></td>
</tr>
</tbody>
</table>


진단 오류 목록은 [Ms-진단 헤더 페이지](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)에서 찾을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

