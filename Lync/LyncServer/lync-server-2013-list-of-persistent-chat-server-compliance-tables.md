---
title: 'Lync Server 2013: 영구 채팅 서버 준수 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df50c94fcf40761247fc647ac8f98ac2d5d4b355
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 준수 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>영구 채팅 서버 준수 테이블 목록


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013의 tblComplianceData</a></p></td>
<td><p>구성된 어댑터에서 아직 처리되지 않은 준수 이벤트를 포함합니다.</p>
<p>이 표에는 채팅 메시지, 파일 다운로드 등의 지속적인 채팅 관련 이벤트가 포함 되어 있습니다. 참가자 이벤트는 tblComplianceParticipant 테이블에서 추적됩니다.</p>
<p>이 테이블의 이벤트를 처리한 서버는 tblComplianceFanout 테이블에 나열됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013의 tblComplianceFanout</a></p></td>
<td><p>준수 이벤트를 처리한 서버를 포함합니다. 이 테이블은 tblComplianceData 테이블과 밀접하게 결합되어 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013의 tblComplianceParticipant</a></p></td>
<td><p>채팅 서비스 및 서버별 현재 참가자를 포함합니다. 영구 채팅 서비스에서 받은 참가 및 파트 준수 이벤트에 따라 유지 관리 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013의 tblComplianceState</a></p></td>
<td><p>풀 전반의 준수 상태 정보를 포함합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

