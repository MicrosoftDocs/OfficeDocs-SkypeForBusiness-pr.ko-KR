---
title: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b763f9b01e070fc434dae997bc1e2da68dcbc26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-07_

이 섹션에서는 프런트 엔드 풀을 배포 하는 데 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다.

<div>

## <a name="dns-records-for-front-end-pools"></a>프런트 엔드 풀에 대 한 DNS 레코드

다음 표에서는 Lync Server 2013 프런트 엔드 풀 배포에 대 한 DNS 요구 사항을 지정 합니다.

### <a name="dns-requirements-for-a-front-end-pool"></a>프런트 엔드 풀에 대 한 DNS 요구 사항

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
<td><p>여러 프런트 엔드 서버와 하드웨어 부하 분산이 있는 프런트 엔드 풀 (DNS 부하 분산이 해당 풀에도 배포 되는지 여부)</p></td>
<td><p>DNS 부하 분산 및 하드웨어 부하 분산 장치를 모두 사용 하는 경우에는 레코드 (A)를 호스트 해야 합니다. DNS 부하 분산을 위해 프런트 엔드 풀의 FQDN (정규화 된 도메인 이름)을 확인 하는 내부 A 레코드를 만듭니다. 내부 웹 서비스에 대 한 내부 호스트 (A) 레코드를 부하 분산 장치의 VIP (가상 IP) 주소에 만듭니다. 토폴로지 작성기에 정의 된 대로 내부 웹 서비스 이름을 사용 해야 합니다.</p>
<p>예를 들어 DNS 로드 밸런싱 및 하드웨어 부하 분산을 모두 사용 하는 경우 DNS 부하 분산을 위한 풀의 각 프런트 엔드 서버에 대 한 레코드와 하드웨어 로드 균형 조정기의 가상 IP를 가리키는 내부 웹 서비스의 A 레코드가 표시 됩니다. :</p>
<ul>
<li><p>DNS 부하 분산: Pool01.contoso.net의 풀 10.10.10.5 IP 주소</p>
<div>

> [!WARNING]  
> 각 프런트 엔드 서버에는 고유한 A 레코드가 있습니다.


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>하드웨어 부하 분산: WebInternal.contoso.net IP 주소 HLB VIP 192.168.10.5</p></li>
</ul>
<p>모든 트래픽 (HTTP/HTTPS 트래픽 제외)은 Pool01.contoso.net 레코드를 사용 합니다. HTTP/HTTPS 트래픽은 192.168.10.5의 정의 된 내부 웹 서비스 주소를 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>DNS 부하 분산이 배포 된 프런트 엔드 풀</p></td>
<td><p>풀의 FQDN을 풀에 있는 각 서버의 IP 주소로 확인 하는 내부 A 레코드 집합입니다. 풀의 각 서버에 대해 하나의 A 레코드가 있어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>DNS 부하 분산이 배포 된 프런트 엔드 풀</p></td>
<td><p>풀에 있는 각 서버의 FQDN을 해당 서버의 IP 주소로 확인 하는 내부 레코드 집합입니다. 자세한 내용은 계획 문서에서 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013의 DNS 부하 분산</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>단일 프런트 엔드 서버 및 전용 백 엔드 데이터베이스를 포함 하는 프런트 엔드 풀 (부하 분산 장치 없음)</p></td>
<td><p>프런트 엔드 풀의 FQDN을 단일 Enterprise Edition 프런트 엔드 서버의 IP 주소로 확인 하는 내부 A 레코드입니다.</p></td>
</tr>
<tr class="odd">
<td><p>자동 클라이언트 로그인</p></td>
<td><p>지원 되는 각 SIP 도메인에 대해 _sipinternaltls에 대 한 SRV 레코드를 _tcp. &lt;로그인&gt; 하는 클라이언트 요청을 인증 하 고 리디렉션하는 프런트 엔드 풀의 FQDN에 매핑되는 포트 5061의 도메인입니다. 자세한 내용은 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항을</a>참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>장치 업데이트 웹 서비스 검색 통합 커뮤니케이션 (UC) 장치</p></td>
<td><p>이름 다중 작업 업데이트-r2를 사용 하는 내부 A 레코드 &lt;장치 업데이트&gt; 웹 서비스를 호스트 하는 프런트 엔드 풀의 IP 주소를 확인 하는 SIP 도메인입니다. UC 장치가 켜져 있지만 사용자가 장치에 로그인 한 적이 없는 경우 A 레코드를 통해 장치가 프런트 엔드 풀 호스팅 장치 업데이트 웹 서비스를 검색 하 고 업데이트를 얻을 수 있습니다. 그렇지 않으면 장치는 사용자가 처음 로그인 할 때 대역내 프로비저닝 기능을 통해이 정보를 가져옵니다.</p>
<div>

> [!IMPORTANT]  
> Lync Server 2010에 장치 업데이트 웹 서비스가 이미 배포 되어 있는 경우에는 이름 작업 업데이트와 함께 내부 A 레코드를 만들었습니다. &lt;SIP 도메인&gt;. Microsoft Office Communications Server 2007 R2의 경우 이름 다중 업데이트-R2를 사용 하 여 추가 DNS A 레코드를 만들어야 합니다. &lt;SIP 도메인&gt;.


</div></td>
</tr>
<tr class="odd">
<td><p>HTTP 트래픽을 지 원하는 리버스 프록시</p></td>
<td><p>외부 웹 팜 FQDN을 리버스 프록시의 외부 IP 주소로 확인 하는 외부 A 레코드입니다. 클라이언트 및 UC 장치이 레코드를 사용 하 여 역방향 프록시에 연결 합니다. 자세한 내용은 계획 설명서의 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</a> 을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


다음 표에는 내부 웹 팜 FQDN에 필요한 DNS 레코드의 예가 나와 있습니다.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>내부 웹 팜 FQDN에 대 한 DNS 레코드 예제

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>내부 웹 팜 FQDN</th>
<th>풀 FQDN</th>
<th>DNS A 레코드 (s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS 프런트 엔드 서버에서 사용 하는 부하 분산 장치의 VIP 주소를 확인 하는 ee-pool.contoso.com에 대 한 A 레코드입니다.</p>
<p>DNS A 프런트 엔드 서버에서 사용 하는 부하 분산 장치에 대 한 VIP 주소를 확인 하는 webcon.contoso.com의 A 레코드입니다.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS A 프런트 엔드 풀의 Enterprise Edition 프런트 엔드 서버에서 사용 하는 부하 분산 장치에 대 한 VIP (가상 IP) 주소를 확인 하는 ee-pool.contoso.com에 대 한 DNS A 레코드입니다.</p>
<p>이 풀에서 DNS 부하 분산을 사용 하는 경우 프런트 엔드 풀과 내부 웹 팜에는 동일한 FQDN을 사용할 수 없습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

