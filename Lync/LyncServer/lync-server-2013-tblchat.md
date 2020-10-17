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
ms.openlocfilehash: f68c638b16ae0e7a253c063351784ce9f7d4d7c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509475"
---
# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013의 tblChat

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblChat에는 모든 채팅 메시지가 포함됩니다.

### <a name="columns"></a>단

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
<td><p>int, null이 아님</p></td>
<td><p>노드 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>Tblchat.chatid</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>tblLastChatId 테이블에서 생성된 대화방 순서를 정의하는 고유한 일련 번호(노드 ID당)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>(가) 날짜</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>채팅 메시지의 타임스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, null이 아님</p></td>
<td><p>게시자의 사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>메시지가 경고 메시지인 경우 True입니다. 그렇지 않으면 False입니다.</p></td>
</tr>
<tr class="even">
<td><p>콘텐츠</p></td>
<td><p>nvarchar(max), null이 아님</p></td>
<td><p>채팅 콘텐츠(일반 텍스트 버전)입니다. 콘텐츠는 일반적으로 일반 텍스트이지만 다음과 같은 예외가 있습니다.</p>
<ul>
<li><p>파일이 ma-filelink: 링크로 표시됩니다.</p></li>
<li><p>링크는 HTML 요소로 표시됩니다(콘텐츠 형식은 HTML로 간주 할 수 없음).</p></li>
<li><p>이야기는 "[STORY]...."와 비슷한 형식으로 인코딩됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar (max)</p></td>
<td><p>채팅 콘텐츠(RTF 버전)입니다. 클라이언트에서 제공하지 않는 경우 Null이 될 수 있습니다.</p></td>
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
<td><p>&lt;channelID,와 (와)&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

