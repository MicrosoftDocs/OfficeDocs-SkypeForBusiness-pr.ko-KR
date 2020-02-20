---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2900a2ca780cfc239cb7045ea564bbba581f2f55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipalAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblPrincipalAffiliations active directory 컨테이너의 도메인에서 Active Directory 도메인 서비스 보안 그룹을 비롯 한 위치에 있는 구성원을 설명 하는 사용자의 소속을 포함 합니다.

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
<td><p>principalID</p></td>
<td><p>int, null이 아님</p></td>
<td><p>연관된 사용자의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int, null이 아님</p></td>
<td><p>회원 정보를 나타내는 사용자의 ID입니다. 각 사용자(system-user-types 제외)에는 self-affiliation도 포함됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>인덱스</p></td>
<td><p>int, null이 아님</p></td>
<td><p>인덱스. 자체 가입 값은-1이 고, 각 &lt;Principalid (affiliationId&gt; 버킷) 내에서 1부터 차례로 증가 하는 다른 인스턴스에 대 한 정보입니다.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, null이 아님</p></td>
<td><p>최근 업데이트를 수행한 사용자입니다. 이 값은 일반적으로 Active Directory 동기화를 의미하는 1입니다.</p></td>
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
<th>단</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

