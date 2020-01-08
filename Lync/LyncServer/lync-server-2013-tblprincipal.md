---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblPrincipal 사용자, 폴더 및 그룹을 비롯 한 모든 사용자를 포함 합니다.

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
<td><p>prinID</p></td>
<td><p>int, null 아님</p></td>
<td><p>Principal ID.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID (null 아님)</p></td>
<td><p>Principal GUID. 이는 해당 의미가 Active Directory 도메인 서비스 공간으로 교차 되므로 대체 기본 키로 광범위 하 게 사용 됩니다. (캐시 된 보안 주체의 GUID는 해당 Active Directory 개체 GUID와 같습니다.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>Principal URI. SIP 스키마는 사용자에 게 사용 되며 ma는 거의 모든 내용에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>일반 이름입니다. 사용자 유형별로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>표시 이름입니다. 사용자 유형별로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회사 이름입니다. 사용자 유형별로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>메일 주소. 사용자 유형별로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>주체가 캐시 된 버전인 Active Directory 개체의 도메인 이름입니다. Active Directory 개체 (예: 시스템 사용자)가 아닌 형식의 경우 Null이 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자의 UPN (사용자 계정 이름). 일반 사용자 형식 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, null이 아님</p></td>
<td><ul>
<li><p>0: 주체가 활성 상태입니다.</p></li>
<li><p>1: 사용자의 SIP 접근 권한 값을 사용할 수 없기 때문에 Principal을 사용할 수 없습니다.</p></li>
<li><p>2: 연결 된 광고 개체가 삭제 되어 주체가 삭제 되었습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>Principal type (tblPrincipalType 테이블에서)</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>주도자에 대 한 Lync 풀 할당입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>태그 유형 정책이 있는 경우 사용자에 대 한 영구 채팅 서버 정책 값</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>작성자의 사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>만든 시간에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>이를 마지막으로 업데이트 한 사용자의 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>마지막 업데이트에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, null 아님</p></td>
<td><p>주도자에 대 한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.</p></td>
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
<th>열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>TblPrincipalType에 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

