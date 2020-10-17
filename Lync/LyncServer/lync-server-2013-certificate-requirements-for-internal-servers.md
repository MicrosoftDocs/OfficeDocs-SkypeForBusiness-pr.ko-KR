---
title: 'Lync Server 2013: 내부 서버에 대 한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526245"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-02-17_

Lync Server를 실행 중이 고 인증서가 필요한 내부 서버에는 Standard Edition Server, Enterprise Edition 프런트 엔드 서버, 중재 서버 및 디렉터가 포함 됩니다. 다음 표에서는 이러한 서버에 대한 인증서 요구 사항을 보여 줍니다. Lync Server 인증서 마법사를 사용 하 여 이러한 인증서를 요청할 수 있습니다.

<div>


> [!TIP]  
> 프런트 엔드 풀, 프런트 엔드 서버 또는 디렉터에서 단순 Url과 관련 된 주체 대체 이름에 대해 와일드 카드 인증서를 사용할 수 있습니다. 와일드 카드 인증서 지원에 대 한 자세한 내용은 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013에서 와일드 카드 인증서 지원을</A>참조 하십시오.



</div>

내부 서버에는 내부 엔터프라이즈 CA(인증 기관)를 사용하는 것이 좋지만 공용 CA를 사용할 수도 있습니다. UC (통합 통신) 인증서에 대 한 특정 요구 사항을 준수 하 고 Microsoft와 제휴 하 여 Lync Server 인증서 마법사를 사용할 수 있도록 하는 인증서를 제공 하는 공용 Ca 목록을 보려면 Microsoft 기술 자료 929395, "Exchange Server 및 통신 서버용 통합 통신 인증서 파트너" 문서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .

Exchange 2013와 같은 다른 응용 프로그램 및 서버와 통신 하려면 다른 응용 프로그램 및 제품에서 지 원하는 인증서가 필요 합니다. 2013 릴리스의 경우 Lync Server 2013 및 기타 Microsoft 서버 제품 (Exchange 2013 및 SharePoint Server 포함)은 서버 간 인증 및 권한 부여를 위한 OAuth (Open Authorization) 프로토콜을 지원 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하십시오.

Windows 7 운영 체제를 실행 하는 클라이언트, Windows Server 2008 운영 체제, Windows Server 2008 R2 운영 체제, Windows Vista 운영 체제 및 Microsoft Lync Phone Edition에 연결 하는 경우 Lync Server 2013에는 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서에 대 한 지원이 포함 됩니다. SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.

다음 표에서는 프런트 엔드 풀 및 Standard Edition Server에 대한 서버 역할별 인증서 요구 사항을 보여 줍니다. 이는 모두 표준 웹 서버 인증서로서, 개인 키를 사용하고 내보낼 수 없습니다.

인증서 마법사를 사용하여 인증서를 요청하면 서버 EKU(확장된 키 사용)가 자동으로 구성됩니다.

<div>


> [!NOTE]  
> 각 인증서 이름은 컴퓨터 저장소에서 고유 해야 합니다.



</div>

<div>


> [!NOTE]  
> DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com를 구성한 경우에는 인증서의 주체 대체 이름에 추가 해야 합니다.



</div>

### <a name="certificates-for-standard-edition-server"></a>Standard Edition Server용 인증서

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>인증서</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예제</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본</p></td>
<td><p>풀의 FQDN(정규화된 도메인 이름)</p></td>
<td><p>풀의 FQDN 및 서버의 FQDN</p>
<p>SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</p>
<p>이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</p></td>
<td><p>SN = se01; SAN = se01</p>
<p>이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</p></td>
<td><p>Standard Edition Server에서는 서버 FQDN이 풀 FQDN과 같습니다.</p>
<p>이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</p>
<p>서버 간 인증에도이 인증서를 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>내부 웹 FQDN(서버의 FQDN과 같음)</p></li>
<li><p>모임 단순 URL</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>관리 단순 URL</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>SN = se01; SAN = se01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</p>
<p>와일드카드 인증서 사용:</p>
<p>SN = se01; SAN = se01; SAN = * .com</p></td>
<td><p>토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수는 없습니다.</p>
<p>모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</p>
<p>와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>SIP 도메인당 단순 Url 충족</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>SN = se01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</p>
<p>와일드카드 인증서 사용:</p>
<p>SN = se01; SAN = webcon01; SAN = * .com</p></td>
<td><p>모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</p>
<p>와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>프런트 엔드 풀의 프런트 엔드 서버용 인증서

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>인증서</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예제</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>풀의 FQDN 및 서버의 FQDN</p>
<p>SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.</p>
<p>이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</p></td>
<td><p>SN = eepool .com; SAN = eepool .com; SAN = ee01</p>
<p>이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</p></td>
<td><p>이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.</p>
<p>서버 간 인증에도이 인증서를 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>내부 웹 FQDN (서버의 FQDN과 같지 않음)</p></li>
<li><p>서버 FQDN</p></li>
<li><p>Lync 풀 FQDN</p></li>
<li><p>모임 단순 URL</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>관리 단순 URL</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>SN = ee01; SAN = ee01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</p>
<p>와일드카드 인증서 사용:</p>
<p>SN = ee01; SAN = ee01; SAN = * .com</p></td>
<td><p>모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</p>
<p>와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>관리 단순 URL</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>SN = ee01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</p>
<p>와일드카드 인증서 사용:</p>
<p>SN = ee01; SAN = webcon01; SAN = * .com</p></td>
<td><p>모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.</p>
<p>와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>디렉터용 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>인증서</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본</p></td>
<td><p>디렉터 풀의 FQDN</p></td>
<td><p>디렉터의 FQDN 및 디렉터 풀의 FQDN</p>
<p>이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01</p>
<p>이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>내부 웹 FQDN(서버의 FQDN과 같음)</p></li>
<li><p>서버 FQDN</p></li>
<li><p>Lync 풀 FQDN</p></li>
<li><p>모임 단순 URL</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>관리 단순 URL</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>SN = dir01; SAN = dir01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.</p>
<p>SN = dir01; SAN = dir01 SAN = * .com</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>각각 다음과 같습니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 단순 URL</p></li>
<li><p>관리 단순 URL</p></li>
<li><p>또는 단순 URL에 대한 와일드카드 항목</p></li>
</ul></td>
<td><p>디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.</p>
<p>SN = dir01; SAN = directorwebcon01 SAN = contoso .com; SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com</p>
<p>SN = dir01; SAN = directorwebcon01 SAN = * .com</p></td>
</tr>
</tbody>
</table>


독립 실행형 중재 서버 풀이 있는 경우 풀의 각 중재 서버에 다음 표에 나열된 인증서가 필요합니다. 중재 서버를 프런트 엔드 서버와 함께 배치한 경우에는 이 항목의 앞부분에서 설명한 "프런트 엔드 풀의 프런트 엔드 서버용 인증서" 표만으로 충분합니다.

### <a name="certificates-for-stand-alone-mediation-server"></a>독립 실행형 중재 서버용 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>인증서</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>풀의 FQDN</p>
<p>풀 구성원 서버의 FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>SBA(Survivable Branch Appliance)용 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>인증서</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본</p></td>
<td><p>SBA의 FQDN</p></td>
<td><p>SIP. &lt; microsoft.rtc.management.xds.sipdomain object &gt; (SIP 도메인 당 하나의 항목 필요)</p></td>
<td><p>SN = sba01; SAN = sip .com; SAN = sip. p m c</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 와일드 카드 인증서 지원](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

