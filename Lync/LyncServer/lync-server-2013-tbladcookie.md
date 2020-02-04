---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>Lync Server 2013의 tblADCookie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-25_

tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.

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
<td><p>prinGuid</p></td>
<td><p>GUID (null 아님)</p></td>
<td><p>모니터링 중인 도메인의 Principal GUID입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (binary)</p></td>
<td><p>Active Directory 동기화 쿠키입니다.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated 됨</p></td>
<td><p>dmtf</p></td>
<td><p>행 업데이트 시간이 포함 된 타임 스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>dmtf</p></td>
<td><p>행이 변경 내용에 맞게 잠길 때 까지의 시간입니다. 이는 채팅 서비스 중 하나만 Active Directory Sync를 한 번에 수행 하도록 하는 소프트웨어 연동 메커니즘의 일부입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>핵심

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>개 열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>PrinGuid 테이블에 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

