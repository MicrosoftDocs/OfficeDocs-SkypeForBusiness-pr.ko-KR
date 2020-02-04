---
title: 'Lync Server 2013: CDR 보기 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe2620175c2a706bfb2c48fe7fb380d5fae4c09
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013의 CDR 보기 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다. 실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 Lync Server의 이전 버전과 호환성을 유지할 가능성이 높기 때문입니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이름 보기</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013의 ClientVersions 보기</a></p></td>
<td><p>통신 세션에 사용 되는 클라이언트 소프트웨어/장치에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013의 ConferenceMessageCount 보기</a></p></td>
<td><p>회의 중 사용자가 보낸 메시지 수에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013의 회의 보기</a></p></td>
<td><p>시작 시간, 종료 시간, 컨퍼런스 이끌이 등 회의 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</a></p></td>
<td><p>시작 및 종료 시간, 사용자 Id, 응답 코드, 진단 Id를 포함 하 여 모든 회의 세션에 대 한 세션 세부 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013의 ConferenceUris 보기</a></p></td>
<td><p>회의에 사용 되는 회의 Uri에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013의 ErrorReport 보기</a></p></td>
<td><p>세션 중에 발생 한 오류에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013의 FileTransfers 보기</a></p></td>
<td><p>파일 이름과 전송 수락, 거부 또는 취소를 포함 하 여 파일 전송 세션에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013의 FocusJoinsAndLeaves 보기</a></p></td>
<td><p>컨퍼런스 참가 및 탈퇴 활동에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013의 McuJoinsAndLeaves 보기</a></p></td>
<td><p>컨퍼런스 참가 및 탈퇴 활동에 대 한 통합 된 정보를 반환 합니다 (각 회의 참가는 해당 회의 연결이 유지 됩니다.).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013의 Mcus 보기</a></p></td>
<td><p>회의 서버에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013의 미디어 보기</a></p></td>
<td><p>피어 투 피어 통신 세션에 사용 되는 미디어 형식에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013의 ProgressReport 보기</a></p></td>
<td><p>완료 된 세션에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013의 등록 보기</a></p></td>
<td><p>Lync Server를 사용 하 여 등록에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 SessionDetails 보기</a></p></td>
<td><p>VoIP 전화 통화, 2 자리 IM 세션 또는 기타 피어 투 피어 통신 세션을 비롯 한 피어 투 피어 세션에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013의 사용자 보기</a></p></td>
<td><p>통신 세션에 참가 한 사용자에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013의 VoIPDetails 보기</a></p></td>
<td><p>하나 이상의 VoIP (음성 over IO) 사용자를 포함 하는 피어 투 피어 세션에 대 한 정보를 반환 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

