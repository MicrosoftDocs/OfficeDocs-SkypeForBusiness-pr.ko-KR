---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013의 tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.

### <a name="columns"></a>열

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이벤트 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, null이 아님</p></td>
<td><p>삽입 시간 (이 경우에는 항목이 자리 표시자 일 수 있으므로 cmplType = 9의 미래입니다).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, null 아님</p></td>
<td><p>준수 이벤트 유형:</p>
<ul>
<li><p>1: 채팅</p></li>
<li><p>2: 백 채팅</p></li>
<li><p>3: 파일 다운로드</p></li>
<li><p>4: 파일 업로드</p></li>
<li><p>9: Provisional 파일 전송</p></li>
<li><p>10: 채팅 삭제 (바꾸기 사용)</p></li>
<li><p>11: 채팅 제거</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이벤트에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), null 아님</p></td>
<td><p>채널 URI (Uniform Resource Identifier)입니다.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>채팅 ID (chatId 테이블에 해당).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, null 아님</p></td>
<td><p>포스터의 Principal ID (tblPrincipal 테이블에 해당)</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), null 아님</p></td>
<td><p>사용자 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>메시지 (인코딩은 cmplType에 따라 다름)</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>키

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

