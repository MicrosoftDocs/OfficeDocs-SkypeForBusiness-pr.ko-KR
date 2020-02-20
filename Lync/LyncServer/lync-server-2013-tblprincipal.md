---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblPrincipal에는 사용자, 폴더 및 그룹을 비롯한 모든 참가자가 포함됩니다.

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
<td><p>Tblprincipal.prinid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>사용자 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>Principal.pringuid</p></td>
<td><p>GUID, null이 아님</p></td>
<td><p>사용자 GUID입니다. 이는 해당 의미가 Active Directory 도메인 서비스 공간에 대 한 것 이므로 대체 기본 키로 광범위 하 게 사용 됩니다. 캐시된 사용자의 GUID는 해당하는 Active Directory 개체 GUID와 동일합니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar(256), null이 아님</p></td>
<td><p>계정 URI입니다. SIP 구성표는 사용자에 대해 사용되고 ma-grp는 거의 모든 다른 항목들에 대해 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>회사 이름입니다. 사용자 유형에서만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar(256)</p></td>
<td><p>표시 이름입니다. 사용자 유형에서만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>회사 이름입니다. 사용자 유형에서만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>전자 메일입니다. 사용자 유형에서만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384)</p></td>
<td><p>계정이 캐시된 버전인 Active Directory 개체의 도메인 이름입니다. Active Directory가 아닌 개체 유형의 경우 Null일 수 있습니다(예: 시스템 사용자).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>사용자의 UPN(Universal Principal Name)입니다. 사용자 유형에서만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, null이 아님</p></td>
<td><ul>
<li><p>0: 계정이 활성입니다.</p></li>
<li><p>1: 사용자의 SIP 기능이 사용하지 않도록 설정되었기 때문에 계정이 사용하지 않도록 설정되었습니다.</p></li>
<li><p>2: 연결된 AD 개체가 삭제되었기 때문에 계정이 삭제되었습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>계정 유형(tblPrincipalType 테이블)입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>임계값</p></td>
<td><p>보안 주체에 대 한 Lync 풀 할당입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>임계값</p></td>
<td><p>사용자에 대 한 영구 채팅 서버 정책 값 (tag type policy가 있는 경우)</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>작성자의 사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>만든 시간에 대한 타임스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>마지막 업데이트에 대한 타임스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, null이 아님</p></td>
<td><p>사용자에 대한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.</p></td>
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
<th>열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tblprincipal.prinid</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>tblPrincipalType.ptypeID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

