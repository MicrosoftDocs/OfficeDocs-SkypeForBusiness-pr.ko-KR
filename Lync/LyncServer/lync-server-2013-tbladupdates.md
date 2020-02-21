---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>Lync Server 2013의 tblADUpdates

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 되지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.

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
<td><p>변경된 개체의 사용자 GUID입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384), null이 아님</p></td>
<td><p>개체의 고유 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>개체의 특성이 하나 이상 변경된 경우 True입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>구성원 자격이 변경된 경우 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>사용되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>개체가 삭제된 경우 True입니다.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, null이 아님</p></td>
<td><p>행이 삽입되었을 때의 타임스탬프입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

