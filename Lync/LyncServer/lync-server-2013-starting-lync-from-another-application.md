---
title: 'Lync Server 2013: 다른 응용 프로그램에서 Lync 시작'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>다른 응용 프로그램에서 Lync 시작

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

명령줄 매개 변수를 사용 하 여 Lync 2013을 빠르게 시작할 수 있습니다. 예를 들어 사용자가 다른 응용 프로그램에서 전화 번호를 클릭 하면 응용 프로그램에서 Lync 2013의 인스턴스를 시작 하 고 해당 번호로 전화를 걸 수 있습니다.

Lync 2013는 단체 회의를 위한 세미콜론으로 구분 된 연락처 이름 목록을 인식할 수도 있습니다.

Lync 2013이 시작 될 때 자동으로 로그인 하도록 구성 된 경우 명령줄 매개 변수를 사용 하 여 Lync 2013을 시작 하면 Lync 주 창이 열립니다. Lync가 시작 될 때 자동으로 로그인 하도록 구성 되어 있지 않으면 로그인 창이 열립니다.

다음 표에서는 사용 가능한 매개 변수를 보여 줍니다.

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 명령줄 매개 변수

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>확장이</th>
<th>데이터 형식</th>
<th>작업</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel</p></td>
<td><p>tel URI</p></td>
<td><p>오디오 통화에 대 한 대화 창을 열고 지정 된 번호로 전화를 걸지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>tel:, sip: 또는 typeable tel URI</p></td>
<td><p>오디오 통화에 대 한 대화 창을 열고 지정 된 번호로 전화를 걸지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>sip</p></td>
<td><p>SIP URI</p></td>
<td><p>참가자 목록에서 지정 된 SIP URI (Uniform Resource Identifier)를 사용 하 여 대화 창을 엽니다.</p></td>
</tr>
<tr class="even">
<td><p>Sip</p></td>
<td><p>SIP URI</p></td>
<td><p>Lync 2013이 TLS (전송 계층 보안) 프로토콜을 사용 하도록 구성 된 경우 sip:와 동일 하 게 작동 합니다. TLS가 사용 되지 않는 경우 높은 수준의 보안이 필요 함을 사용자에 게 알리는 대화 상자가 표시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>회의</p></td>
<td><p>참가할 회의 SIP URI</p></td>
<td><p>URI가 자체 이면 포커스를 인스턴스화하고 명단 전용 보기를 엽니다. 그렇지 않으면 명단 보기를 표시 하지만 초대를 보내지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>메시징</p></td>
<td><p>SIP URI</p></td>
<td><p>인스턴트 메시징 (IM) 대화 창을 SIP URI와 함께 표시 합니다. 구분 기호 없이 꺾쇠 괄호 () 안에 지정&lt;&gt;된 여러 SIP uri를 허용 합니다.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


다음 표에 이러한 명령줄 매개 변수의 예가 나와 있습니다.

### <a name="command-line-parameter-examples"></a>명령줄 매개 변수 예제

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>인스턴스</th>
<th>하면</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>+ 14255550101를 사용 하 여 전화 전용 보기를 엽니다.</p></td>
</tr>
<tr class="even">
<td><p>Callto tel: + 14255550101</p></td>
<td><p>+ 14255550101를 사용 하 여 전화 전용 보기를 엽니다.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Kazuto@litwareinc.com를 사용 하 여 전화 전용 보기를 엽니다.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Kazuto@litwareinc.com 있는 대화 창을 엽니다.</p></td>
</tr>
<tr class="odd">
<td><p>회의: sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>대화 창을 열고 모임 오디오 참가 옵션을 표시 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

