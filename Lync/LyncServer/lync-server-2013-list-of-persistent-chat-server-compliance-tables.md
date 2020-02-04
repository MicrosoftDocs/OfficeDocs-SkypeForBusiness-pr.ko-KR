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
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 준수 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

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
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013의 tblComplianceData</a></p></td>
<td><p>구성 된 어댑터에서 아직 처리 하지 않은 준수 이벤트를 포함 합니다.</p>
<p>이 표에는 채팅 메시지 및 파일 다운로드와 같은 지속적인 채팅 관련 이벤트가 포함 되어 있습니다. (참가자 이벤트는 tblComplianceParticipant 테이블에서 추적 됩니다.)</p>
<p>(이 테이블의 이벤트를 처리 하는 서버는 tblComplianceFanout 테이블에 나열 되어 있습니다.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013의 tblComplianceFanout</a></p></td>
<td><p>규정 준수 이벤트를 처리 한 서버를 포함 합니다. 이 표는 tblComplianceData 테이블과 밀접 하 게 결합 되어 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013의 tblComplianceParticipant</a></p></td>
<td><p>채팅 서비스 및 서버 별로 현재 참가자가 포함 되어 있습니다. 영구 채팅 서비스에서 받은 참가 및 파트 규정 준수 이벤트에 따라 유지 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013의 tblComplianceState</a></p></td>
<td><p>풀 전체의 준수 상태 정보를 포함 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

