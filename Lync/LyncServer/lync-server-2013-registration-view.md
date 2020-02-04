---
title: 'Lync Server 2013: 등록 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120f0cb40bb3401a327e495a460db400a9359891
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Lync Server 2013의 등록 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

등록 보기에는 사용자 등록에 대 한 정보가 저장 됩니다. 이 보기는 Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>등록이 발생 한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>등록 된 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 된 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 된 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>등록 된 사용자의 끝점에 대 한 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>dmtf</p></td>
<td><p>등록 취소가 발생 한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 취소 이유.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 한 사용자가 사용 하는 클라이언트 버전입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>등록 한 사용자가 사용 하는 클라이언트 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>등록 하는 사용자가 사용 하는 클라이언트의 범주입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IpAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 등록 된 IP 주소입니다. IPv4 또는 IPv6 주소를 사용할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>SIP 대화 상자 ID입니다. 의 형식은 다음과 같습니다.</p>
<p>대화 상자; from 태그; 태그</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 헤더에서 진단 ID를 캡처 했습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>레지스터</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록자의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>풀</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 된 사용자가 사용 하는 Edge 서버의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>다소</p></td>
<td><p>사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable 가능</strong></p></td>
<td><p>다소</p></td>
<td><p>등록할 때 UserService를 사용할 수 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>다소</p></td>
<td><p>등록이 기본 등록자를 사용 하 고 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>등록 된 디바이스의 MAC 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 된 디바이스의 제조업체입니다. 자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 된 디바이스의 하드웨어 버전입니다. 자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

