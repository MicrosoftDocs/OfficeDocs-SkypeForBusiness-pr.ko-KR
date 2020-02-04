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
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 진단 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

진단 보고서는 실패 한 세션에 대 한 진단 및 문제 해결 정보를 제공 합니다. 이 정보에는 진단 ID와 세션에 실패 했을 때 보고 된 진단 헤더가 모두 포함 됩니다. 진단 ID는 SIP 메시지에 연결 되는 고유 식별자 (ms-진단 헤더 형식) 이며 진단 헤더는 진단 ID에 대해 함께 설명 합니다. 보고 구성 요소에서 인식 하는 중요 한 문제 해결 세부 정보를 보고서에 포함할 수도 있습니다. 예를 들면 다음과 같습니다.

  - 오류를 생성 한 PSTN 게이트웨이에서 제공 하는 원인 코드입니다. PSTN 네트워크에서 발신 통화가 실패 하면, ISDN 사용자 파트 (ISUP)가 자동으로 생성 됩니다. 예를 들어 PSTN 게이트웨이에서는 통화를 완료 하는 데 사용할 수 있는 회로 또는 채널이 없음을 나타내기 위해 코드 34를 보낼 수 있습니다.

  - 연결 오류에 대 한 피어 FQDN, 포트 및 Winsock 오류.

  - DNS 확인 실패를 조회 하는 이름입니다. DNS 확인은 클라이언트가 이름 서버에 접속 하 고 지정 된 디바이스 이름에 해당 하는 IP 주소를 요청 하는 경우에 발생 합니다.

<div>

## <a name="accessing-the-diagnostic-report"></a>진단 보고서에 액세스

[Lync Server 2013의 피어 투 피어 세션 세부 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 또는 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

없음. 진단 보고서는 필터링 할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 진단 보고서에서 각 세션에 대해 제공 하는 정보가 나열 되어 있습니다.

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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>보고서 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>보고서가 기록 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>응답 코드</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>요청 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 SIP 요청 유형입니다. 예를 들어 초대, BYE, 서비스 등이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류의 원본입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 URI에서</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 에이전트에서</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>콘텐츠 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 미디어 콘텐츠의 유형입니다. 예를 들어 공용 콘텐츠 형식은 Application/sdp입니다. SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응용 프로그램</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류와 관련 된 응용 프로그램</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 URI로</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 초대 된 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p>컨퍼런스 참가 시간 (ms)</p></td>
<td><p>아니요</p></td>
<td><p>사용자가 회의에 참가 하는 데 걸린 시간 (밀리초 단위)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 헤더</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 ID 설명입니다.</p></td>
</tr>
</tbody>
</table>


진단 오류 목록은 [Ms-진단 헤더 페이지](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)에서 찾을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

