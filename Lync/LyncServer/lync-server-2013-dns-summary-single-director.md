---
title: 'Lync Server 2013: DNS 요약-단일 디렉터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692cfd5f04a80a674fffb5e3a0f2f1890309c371
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약-단일 디렉터

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

다음 표에는 단일 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 포함 되어 있습니다. 디렉터 역할에는 프런트 엔드 서버로 서 유사한 DNS 레코드가 필요 합니다. 필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다. 프런트 엔드 서버와 달리 디렉터는 사용자 계정을 호스트 하거나 모바일 서비스를 호스트 하지 않습니다.

### <a name="dns-records-required-for-the-director"></a>디렉터에 필요한 DNS 레코드

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN/DNS 레코드</th>
<th>IP 주소/FQDN</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>영화</p></td>
<td><p>복제 및 서버 간 서버에 사용 되는 디렉터 호스트 레코드</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>영화</p></td>
<td><p>에 지 서버의 내부에 지 인터페이스에서 인바운드 SIP (세션 시작 프로토콜)</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>영화</p></td>
<td><p>역방향 프록시에서 게시된 전화 접속 웹 서비스</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>영화</p></td>
<td><p>역방향 프록시에서 게시된 모임 웹 서비스</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>영화</p></td>
<td><p>디렉터에 대 한 역방향 프록시 웹 티켓 외부 웹 서비스에서 게시 및 정의 됨</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

