---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6070f6a575466d9ce7063c588e5d470e047d52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523815"
---
# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013의 tblNode

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblNode에는 Lync Server 2013 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 대화방 노드 포함)가 포함 되어 있습니다.

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
<td><p>입니다</p></td>
<td><p>int, null이 아님</p></td>
<td><p>노드 ID(고유 번호)입니다.</p></td>
</tr>
<tr class="even">
<td><p>Tblnode.nodeguid</p></td>
<td><p>GUID, null이 아님</p></td>
<td><p>노드 GUID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>아닌 parentid</p></td>
<td><p>int</p></td>
<td><p>부모의 노드 ID입니다. 루트 노드(ID 1)는 그 자신을 부모로 포함합니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>노드가 범주인 경우 True입니다.</p>
<p>노드가 대화방인 경우 False입니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar(256), null이 아님</p></td>
<td><p>노드 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar(256), null이 아님</p></td>
<td><p>노드 설명입니다.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>비트만</p></td>
<td><p>범주인 경우:</p>
<ul>
<li><p>초대가 설정된 경우 True입니다.</p></li>
<li><p>초대가 해제된 경우 False입니다.</p></li>
</ul>
<p>대화방인 경우:</p>
<ul>
<li><p>초대가 해제된 경우 False입니다(부모 범주 재정의).</p></li>
<li><p>부모 범주에서 초대 설정이 상속된 경우 Null입니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>된다</p></td>
<td><p>비트만</p></td>
<td><p>범주인 경우:</p>
<ul>
<li><p>대화 기록이 설정된 경우 True입니다.</p></li>
<li><p>대화 기록이 해제된 경우 Fasle입니다.</p></li>
</ul>
<p>대화방인 경우:</p>
<ul>
<li><p>아니어야.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>비트만</p></td>
<td><p>범주인 경우:</p>
<ul>
<li><p>파일 업로드가 허용된 경우 True입니다.</p></li>
<li><p>파일 업로드가 허용되지 않은 경우 False입니다.</p></li>
</ul>
<p>대화방인 경우:</p>
<ul>
<li><p>아니어야.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>비활성화됨</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>대화방이 비활성화된 경우 True입니다. 대화방에만 적용됩니다. 범주의 경우 False입니다.</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>동작과</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>동작(EnumValue 테이블에서 조회됨):</p>
<ul>
<li><p>4: 일반(일반 대화방)</p></li>
<li><p>5: 강당(강당 대화방, 발표자만 기여할 수 있음)</p></li>
</ul>
<p>대화방에만 적용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>잘</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>표시 유형(EnumValue 테이블에서 조회됨):</p>
<ul>
<li><p>2: 개인</p></li>
<li><p>3: 범위 지정</p></li>
<li><p>6: 열려 있음</p></li>
</ul>
<p>대화방에만 적용됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Tblsiopwhitelist.siopid</p></td>
<td><p>GUID</p></td>
<td><p>추가 기능이 이 대화방과 연결된 경우 추가 기능 GUID입니다. (범주에는 추가 기능이 없습니다.)</p>
<p>추가 기능 정보는 SiopWhiteList 테이블에서 조회됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, null이 아님</p></td>
<td><p>이 노드를 만든 사용자의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>노드 작성의 타임스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, null이 아님</p></td>
<td><p>이 노드를 마지막으로 업데이트한 사용자의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이 노드를 마지막으로 업데이트한 타임스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>이 노드에 영향을 준 최근의 삭제 작업(ScopedPrincipal 테이블에서 범위 및 PrincipalRole 테이블에서 역할 제거)의 시간입니다. 채팅 서비스의 내부 캐시 업데이트 메커니즘에서 사용됩니다.</p></td>
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
<td><p>입니다</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>동작과</p></td>
<td><p>tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>잘</p></td>
<td><p>tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>아닌 parentid</p></td>
<td><p>tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Tblsiopwhitelist.siopid</p></td>
<td><p>tblSiopWhiteList.siopId 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

