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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>Lync Server 2013의 tblADCookie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-25_

tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.

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
<th>형식</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Principal.pringuid</p></td>
<td><p>GUID, null이 아님</p></td>
<td><p>모니터링 중인 도메인의 사용자 GUID입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar(255)</p></td>
<td><p>Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image(바이너리)</p></td>
<td><p>Active Directory 동기화 쿠키입니다.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>행 업데이트 시간이 포함된 타임스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>변경할 수 없도록 행이 잠길 때까지의 시간입니다. 이 방식은 한 번에 하나의 채팅 서비스만 Active Directory 동기화를 수행할 수 있도록 보장하는 소프트웨어 내부 잠금 메커니즘입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>키

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>열 (s)</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Principal.pringuid</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>Principal.pringuid</p></td>
<td><p>Principal.prinGuid 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

