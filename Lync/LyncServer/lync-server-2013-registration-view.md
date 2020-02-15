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
ms.openlocfilehash: a7418c5aa80e35d783517a86626dd2b77a393e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Lync Server 2013의 등록 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

등록 보기에는 사용자 등록에 대한 정보가 저장됩니다. 이 보기는 Lync Server 2013에 도입 되었습니다.


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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>등록이 발생한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>변수와 useruri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>등록한 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userurit<</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록한 사용자 URI의 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록한 사용자의 테넌트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>고유</p></td>
<td><p>등록한 사용자의 끝점에 대한 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>고유</p></td>
<td><p>동일 사용자 및 동일 끝점이 포함된 등록을 구분하는 데 사용되는 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>등록 취소가 발생한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록 취소에 대한 이유입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록한 사용자가 사용한 클라이언트 버전입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>등록한 사용자가 사용한 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>등록한 사용자가 사용한 클라이언트의 범주입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Address</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 등록한 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>SIP 대화 ID입니다. 형식은 다음과 같습니다.</p>
<p>대화 상자, from 태그; to 태그</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 헤더에서 캡처된 진단 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>등록자</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록자의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>그룹</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록한 사용자가 사용한 에지 서버의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>비트만</p></td>
<td><p>사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>비트만</p></td>
<td><p>등록 시에 UserService를 사용할 수 있었는지를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>비트만</p></td>
<td><p>기본 등록자로 등록이 수행되었는지를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>등록된 장치의 MAC 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록된 장치의 제조업체입니다. 자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>등록된 장치의 하드웨어 버전입니다. 자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

