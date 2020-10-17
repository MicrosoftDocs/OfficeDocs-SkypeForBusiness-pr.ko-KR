---
title: 'Lync Server 2013: 등록 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c40fddd324cd687b54d0c3317edc533fa559c8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536695"
---
# <a name="registration-table-in-lync-server-2013"></a>Lync Server 2013의 정합 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

각 레코드는 한 사용자의 등록 이벤트를 나타냅니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>키/인덱스</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션 요청 시간입니다. <strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>사용자 ID입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>고유</p></td>
<td></td>
<td><p>등록 끝점을 식별하기 위한 GUID입니다. 일반적으로 동일 사용자 및 동일 컴퓨터의 등록 이벤트는 동일한 끝점 ID를 갖습니다. 컴퓨터가 다른 경우 서로 다른 끝점 ID를 갖습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>고유</p></td>
<td></td>
<td><p>같은 사용자 및 끝점을 포함하는 등록을 구분하는 데 사용되는 ID입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>현재 사용자의 클라이언트 버전입니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>등록에 사용된 등록자 서버의 ID입니다. 자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션이 캡처된 풀의 ID입니다. 자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>등록이 수행되는 에지 서버입니다. 자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>사용자가 내부로부터 로그온되었는지 여부입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>UserService를 사용할 수 있는지 여부입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>기본 등록자에 등록할지 여부입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>사용자가 SBA(Survivable Branch Appliance)에 등록되는지 여부를 나타냅니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>등록 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>등록 취소 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>등록 요청의 응답 코드입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>등록 요청의 진단 ID입니다. 이 값은 진단 정보 유형을 표시합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>등록 요청이 시작된 장치입니다. 자세한 내용은 <a href="lync-server-2013-devices-table.md">Lync Server 2013에서 Devices 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p>'사용자 시작', '등록 만료', '클라이언트 오류' 등의 등록 취소 이유입니다. 자세한 내용은 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>사용자가 등록된 끝점의 IP 주소입니다. IPv4 주소 또는 IPv6 주소일 수 있습니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

