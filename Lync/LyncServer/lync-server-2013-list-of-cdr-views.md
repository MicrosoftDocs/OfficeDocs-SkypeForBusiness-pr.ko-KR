---
title: 'Lync Server 2013: CDR 보기 목록'
description: 'Lync Server 2013: CDR 보기 목록'
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
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550084"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013의 CDR 보기 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

보기는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다. 실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 작성 하는 데 보기를 사용 하는 것이 좋습니다. 데이터베이스 보기는 이후 Lync Server의 릴리스와 이전 버전과의 호환성을 유지 하는 것이 더 쉽습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>보기 이름</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013의 ClientVersions 보기</a></p></td>
<td><p>통신 세션에서 사용되는 클라이언트 소프트웨어/장치에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013의 ConferenceMessageCount 보기</a></p></td>
<td><p>전화 회의에서 사용자가 보낸 메시지 수에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013의 회의 보기</a></p></td>
<td><p>시작 시간, 종료 시간, 전화 회의 이끌이 등의 전화 회의 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</a></p></td>
<td><p>시작/종료 시간, 사용자 ID, 응답 코드, 진단 ID를 포함하여 모든 전화 회의 세션에 대한 세션 세부 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013의 ConferenceUris 보기</a></p></td>
<td><p>전화 회의에서 사용되는 전화 회의 URI에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013의 ErrorReport 보기</a></p></td>
<td><p>세션 중 발생한 오류에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013의 FileTransfers 보기</a></p></td>
<td><p>파일 이름 및 전송 수락/거절/취소 여부를 포함하여 파일 전송 세션에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013의 FocusJoinsAndLeaves 보기</a></p></td>
<td><p>전화 회의 참가 및 나가기 활동에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013의 McuJoinsAndLeaves 보기</a></p></td>
<td><p>전화 회의 참가 및 나가기 활동에 대한 결합된 정보를 반환합니다(각 전화 회의 참가는 해당하는 전화 회의 나가기와 쌍으로 지정됨).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013의 Mcus 보기</a></p></td>
<td><p>전화 회의 서버에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013의 미디어 보기</a></p></td>
<td><p>피어 투 피어 통신 세션에서 사용되는 미디어 유형에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013의 ProgressReport 보기</a></p></td>
<td><p>완료된 세션에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013의 등록 보기</a></p></td>
<td><p>Lync Server를 사용 하 여 등록에 대 한 정보를 반환 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 SessionDetails 보기</a></p></td>
<td><p>VoIP 간 전화 통화, 두 사용자 간의 IM 세션 또는 기타 피어 투 피어 통신 세션을 포함하여 피어 투 피어 세션에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013의 사용자 보기</a></p></td>
<td><p>통신 세션에 참가한 사용자에 대한 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013의 VoIPDetails 보기</a></p></td>
<td><p>VoIP(Voice over IP) 사용자가 한 명 이상 포함된 피어 투 피어 세션에 대한 정보를 반환합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

