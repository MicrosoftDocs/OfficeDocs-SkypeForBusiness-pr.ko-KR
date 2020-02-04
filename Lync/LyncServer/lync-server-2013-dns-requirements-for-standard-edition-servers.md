---
title: 'Lync Server 2013: Standard Edition 서버에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3132ec1e18d27564f0077e83d411c5b3930c241b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013의 Standard Edition server에 대 한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-19_

이 섹션에서는 Standard Edition 서버 배포에 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>스탠더드 버전 서버에 대 한 DNS 레코드

다음 표에서는 Lync Server 2013 Standard Edition server 배포에 대 한 DNS 요구 사항을 지정 합니다.

### <a name="dns-requirements-for-a-standard-edition-server"></a>스탠더드 버전 서버에 대 한 DNS 요구 사항

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>배포 시나리오</th>
<th>DNS 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>스탠더드 버전 서버</p></td>
<td><p>서버의 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.</p></td>
</tr>
<tr class="even">
<td><p>자동 클라이언트 로그인</p></td>
<td><p>지원 되는 각 SIP 도메인에 대해 _sipinternaltls에 대 한 SRV 레코드를 _tcp. &lt;로그인&gt; 하는 클라이언트 요청을 인증 하 고 리디렉션하는 Standard Edition 서버의 FQDN에 매핑되는 포트 5061의 도메인입니다. 자세한 내용은 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항을</a>참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>장치 업데이트 웹 서비스 검색 통합 커뮤니케이션 (UC) 장치</p></td>
<td><p>이름 다중 작업 업데이트-r2를 사용 하는 내부 A 레코드 &lt;장치 업데이트&gt; 웹 서비스의 STANDARD Edition server 호스팅 IP 주소를 확인 하는 SIP 도메인입니다. UC 장치가 켜져 있지만 사용자가 장치에 로그인 한 적이 없는 경우에는 A 레코드를 통해 장치가 장치 업데이트 웹 서비스를 호스팅하는 서버를 검색 하 고 업데이트를 얻을 수 있습니다. 그렇지 않으면 장치는 사용자가 처음 로그인 할 때 대역내 프로비저닝 기능을 통해 서버 정보를 가져옵니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTP 트래픽을 지 원하는 리버스 프록시</p></td>
<td><p>외부 웹 팜 FQDN을 리버스 프록시의 외부 IP 주소로 확인 하는 외부 A 레코드입니다. 클라이언트 및 UC 장치이 레코드를 사용 하 여 역방향 프록시에 연결 합니다. 자세한 내용은 계획 설명서의 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</a> 을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

