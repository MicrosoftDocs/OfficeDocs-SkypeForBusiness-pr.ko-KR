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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013의 tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblNode에는 Lync Server 2013 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 채팅방 노드가 있음)가 포함 되어 있습니다.

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
<td><p>nodeID</p></td>
<td><p>int, null 아님</p></td>
<td><p>노드 ID (고유 번호).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID (null 아님)</p></td>
<td><p>노드 GUID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>부모의 노드 ID입니다. 루트 노드 (ID 1)는 자신을 부모로도 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p>종류</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>노드가 범주 이면 True입니다.</p>
<p>노드가 채팅방 이면 False입니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>노드 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>노드 설명입니다.</p></td>
</tr>
<tr class="odd">
<td><p>있도록</p></td>
<td><p>다소</p></td>
<td><p>범주:</p>
<ul>
<li><p>초대가 설정 된 경우 True입니다.</p></li>
<li><p>초대가 해제 된 경우 False입니다.</p></li>
</ul>
<p>회의실:</p>
<ul>
<li><p>초대가 해제 된 경우 False (상위 범주 무시)</p></li>
<li><p>초대 설정이 상위 범주에서 상속 되는 경우 Null입니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>사람이</p></td>
<td><p>다소</p></td>
<td><p>범주:</p>
<ul>
<li><p>채팅 내역이 켜져 있는 경우 True입니다.</p></li>
<li><p>대화 내용이 설정 되어 있지 않으면 False입니다.</p></li>
</ul>
<p>회의실:</p>
<ul>
<li><p>L.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>다소</p></td>
<td><p>범주:</p>
<ul>
<li><p>파일 업로드가 허용 되는 경우 True입니다.</p></li>
<li><p>False 이면 파일 업로드를 허용 하지 않습니다.</p></li>
</ul>
<p>회의실:</p>
<ul>
<li><p>L.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>비활성화</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>채팅방을 사용할 수 없는 경우 True입니다. 채팅방에만 적용 됩니다. (범주에 대 한 False)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>결과가</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>동작 (EnumValue 테이블에서 조회):</p>
<ul>
<li><p>4: 보통 (일반 채팅방).</p></li>
<li><p>5: Auditorium (Auditorium 채팅방은 발표자만 참가할 수 있습니다.)</p></li>
</ul>
<p>채팅방에만 적용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>시도가</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>가시성 (EnumValue 표를 통해 조회):</p>
<ul>
<li><p>2: 비공개</p></li>
<li><p>3: 범위 지정</p></li>
<li><p>6: 열림</p></li>
</ul>
<p>채팅방에만 적용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>SHAP</p></td>
<td><p>추가 기능 GUID가이 채팅방과 연결 되어 있는 경우이를 사용 합니다. (범주에는 추가 기능이 없습니다.)</p>
<p>추가 기능 정보는 SiopWhiteList 테이블에서 조회 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, null 아님</p></td>
<td><p>이 노드를 만든 사용자의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>노드 생성에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, null 아님</p></td>
<td><p>이 노드의 최신 업데이트를 수행한 사용자의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이 노드의 최신 업데이트에 대 한 타임 스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>dmtf</p></td>
<td><p>이 노드에 영향을 주는 최신 지우기 작업의 시간 (tblScopedPrincipal table의 범위 제거 및 tblPrincipalRole 테이블에서 가져온 역할) 이는 채팅 서비스의 내부 캐시 업데이트 메커니즘에 사용 됩니다.</p></td>
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
<td><p>nodeID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>결과가</p></td>
<td><p>TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>시도가</p></td>
<td><p>TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>NodeID 테이블에 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>TblSiopWhiteList의 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

