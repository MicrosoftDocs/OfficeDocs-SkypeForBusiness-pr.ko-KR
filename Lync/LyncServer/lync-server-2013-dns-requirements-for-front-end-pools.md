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
ms.openlocfilehash: a1808e4b65e900b5a38de1d76e7da17fe055d270
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526835"
---
# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-07_

이 섹션에서는 프런트 엔드 풀을 배포하는 데 필요한 DNS(도메인 이름 시스템) 레코드에 대해 설명합니다.

<div>

## <a name="dns-records-for-front-end-pools"></a>프런트 엔드 풀에 대한 DNS 레코드

다음 표에서는 Lync Server 2013 프런트 엔드 풀 배포에 대 한 DNS 요구 사항을 지정 합니다.

### <a name="dns-requirements-for-a-front-end-pool"></a>프런트 엔드 풀에 대한 DNS 요구 사항

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
<td><p>여러 프런트 엔드 서버 및 하나의 하드웨어 분산 장치가 포함된 프런트 엔드 풀(DNS 부하 분산이 해당 풀에 배포되었는지 여부는 상관없음)</p></td>
<td><p>DNS 부하 분산과 하드웨어 부하 분산 장치를 모두 사용하는 경우 호스트(A) 레코드가 필요합니다. DNS 부하 분산을 위한 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)으로 확인되는 내부 A 레코드를 만듭니다. 부하 분산 장치의 VIP(가상 IP 주소)를 가리키는 내부 웹 서비스의 내부 호스트(A) 레코드를 만듭니다. 토폴로지 작성기에 정의 된 대로 내부 웹 서비스 이름을 사용 해야 합니다.</p>
<p>예를 들어 DNS 부하 분산 및 하드웨어 부하 분산을 모두 사용 하는 경우 DNS 부하 분산을 위해 풀의 각 프런트 엔드 서버에 대 한 A 레코드와 하드웨어 부하 분산 장치의 가상 IP를 가리키는 내부 웹 서비스에 대 한 A 레코드가 있어야 합니다.</p>
<ul>
<li><p>DNS 부하 분산:   Pool01.contoso.net   풀의 IP 주소   10.10.10.5</p>
<div>

> [!WARNING]  
> 각 프런트 엔드 서버에는 다음과 같은 고유한 A 레코드가 있습니다.


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>하드웨어 부하 분산:   WebInternal.contoso.net   HLB의 IP 주소(VIP)   192.168.10.5</p></li>
</ul>
<p>HTTP/HTTPS 트래픽을 제외한 모든 트래픽은 Pool01.contoso.net 레코드를 사용합니다. HTTP/HTTPS 트래픽은 정의된 내부 웹 서비스 주소인 192.168.10.5를 사용합니다.</p></td>
</tr>
<tr class="even">
<td><p>DNS 부하 분산이 배포된 프런트 엔드 풀</p></td>
<td><p>풀의 FQDN을 풀에 있는 각 서버의 IP 주소로 확인하는 내부 A 레코드 집합. 풀에는 서버당 하나의 A 레코드가 포함될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>DNS 부하 분산이 배포된 프런트 엔드 풀</p></td>
<td><p>풀의 각 서버에 대한 FQDN을 해당 서버의 IP 주소로 확인하는 내부 A 레코드 집합. 자세한 내용은 계획 설명서에서 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013의 DNS 부하 분산</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>단일 프런트 엔드 서버와 전용 백 엔드 데이터베이스를 포함하지만 부하 분산 장치는 포함하지 않는 프런트 엔드 풀</p></td>
<td><p>프런트 엔드 풀의 FQDN을 단일 Enterprise Edition 프런트 엔드 서버의 IP 주소로 확인하는 내부 A 레코드</p></td>
</tr>
<tr class="odd">
<td><p>자동 클라이언트 로그인</p></td>
<td><p>지원 되는 각 SIP 도메인에 대해 _sipinternaltls에 대 한 SRV 레코드 _tcp. &gt;로그인 하는 클라이언트 요청을 인증 하 고 리디렉션하는 프런트 엔드 풀의 FQDN에 매핑되는 포트 5061의 도메인입니다. 자세한 내용은 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항을</a>참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>UC(통합 통신) 장치를 통한 장치 업데이트 웹 서비스 검색</p></td>
<td><p>이름이 &lt; c s p 2 인 내부 A 레코드 &gt; 장치 업데이트 웹 서비스를 호스트 하는 프런트 엔드 풀의 IP 주소로 확인 되는 SIP 도메인입니다. UC 장치가 설정되었지만 사용자가 장치에 로그인하지 않은 상황에서 A 레코드를 사용하면 장치가 장치 업데이트 웹 서비스를 호스팅하는 프런트 엔드 풀을 검색하고 업데이트를 가져올 수 있습니다. 그렇지 않으면 장치는 사용자가 처음 로그인할 때 인밴드 구축을 통해 이 정보를 가져옵니다.</p>
<div>

> [!IMPORTANT]  
> Lync Server 2010에 기존에 장치 업데이트 웹 서비스가 배포 되어 있는 경우에는 이름이 c s e r e r e r 있는 내부 A 레코드를 이미 만든 것입니다. &lt; SIP 도메인 &gt; Microsoft Office Communications Server 2007 r 2의 경우에는 이름 다중 업데이트-2와 함께 추가 DNS A 레코드를 만들어야 합니다. &lt; SIP 도메인 &gt;


</div></td>
</tr>
<tr class="odd">
<td><p>HTTP 트래픽을 지원하는 역방향 프록시</p></td>
<td><p>외부 웹 팜 FQDN을 역방향 프록시의 외부 IP 주소로 확인하는 외부 A 레코드. 클라이언트와 UC 장치는 이 레코드를 사용하여 역방향 프록시에 연결합니다. 자세한 내용은 계획 설명서에서 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</a> 을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 내부 웹 팜 FQDN에 필요한 DNS 레코드의 예를 보여 줍니다.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>내부 웹 팜 FQDN에 필요한 DNS 레코드의 예

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
<th>DNS A 레코드</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP 주소로 확인되는 ee-pool.contoso.com에 대한 DNS A 레코드</p>
<p>프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP 주소로 확인되는 webcon.contoso.com에 대한 DNS A 레코드</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>프런트 엔드 풀에서 Enterprise Edition 프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP(가상 IP) 주소로 확인되는 ee-pool.contoso.com에 대한 DNS A 레코드</p>
<p>이 풀에서 DNS 부하 분산을 사용하는 경우에는 프런트 엔드 풀과 내부 웹 팜의 FQDN이 동일할 수 없습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

