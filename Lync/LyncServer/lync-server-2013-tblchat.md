---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f3879924b37fa535973116af599f4713c58a207
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013의 tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblChat에는 모든 채팅 메시지가 포함 됩니다.

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
<td><p>channelId</p></td>
<td><p>int, null 아님</p></td>
<td><p>노드 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>TblLastChatId 테이블에서 생성 된 채팅방 순서를 정의 하는 고유 순차 번호 (노드 ID 당)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>로이 날짜</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>채팅 메시지에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, null 아님</p></td>
<td><p>포스터의 사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>메시지가 알림 메시지 이면 True를 지정 합니다. 그렇지 않으면 False입니다.</p></td>
</tr>
<tr class="even">
<td><p>콘텐트가</p></td>
<td><p>nvarchar (max), null 아님</p></td>
<td><p>채팅 콘텐츠 (일반 텍스트 버전). 일반적으로 콘텐츠는 다음과 같은 예외를 포함 하는 일반 텍스트로 되어 있습니다.</p>
<ul>
<li><p>파일은 ma-filelink: 링크로 표시 됩니다.</p></li>
<li><p>링크는 HTML 요소로 표시 됩니다 (콘텐츠 형식을 HTML로 간주할 수 없음).</p></li>
<li><p>스토리는 "[스토리] ..."와 같은 형식으로 인코딩됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>서식</p></td>
<td><p>varchar (max)</p></td>
<td><p>채팅 콘텐츠 (RTF 버전). 클라이언트가 제공 하지 않는 경우 Null 일 수 있습니다.</p></td>
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
<td><p>&lt;channelID,로 d&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

