---
title: 'Lync Server 2013: 내부 서버에 대한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013의 내부 서버에 대한 인증서 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-02-17_

Lync Server를 실행 중이 고 인증서가 필요한 내부 서버에는 표준 버전 서버, Enterprise Edition 프런트 엔드 서버, 중재 서버, 이사 등이 포함 됩니다. 다음 표에는 이러한 서버에 대 한 인증서 요구 사항이 나와 있습니다. Lync 서버 인증서 마법사를 사용 하 여 이러한 인증서를 요청할 수 있습니다.

<div>


> [!TIP]  
> 와일드 카드 인증서는 프런트 엔드 풀, 프런트 엔드 서버 또는 디렉터에 있는 간단한 Url과 연결 된 주체 대체 이름에 대해 지원 됩니다. 와일드 카드 인증서 지원에 대 한 자세한 내용은 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013의 와일드 카드 인증서 지원을</A>참조 하세요.



</div>

내부 서버에는 내부 엔터프라이즈 CA (인증 기관)가 권장 되지만 공용 CA를 사용할 수도 있습니다. UC (통합 커뮤니케이션) 인증서에 대 한 특정 요구 사항을 준수 하 고 Lync Server 인증서 마법사와 함께 사용할 수 있도록 Microsoft와 제휴 하는 인증서를 제공 하는 공개 Ca 목록은 Microsoft 기술 자료 929395, "Exchange Server 및 통신 서버용 통합 커뮤니케이션 인증서 파트너" 문서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).

Exchange 2013와 같은 다른 응용 프로그램 및 서버와의 통신에는 다른 응용 프로그램 및 제품에서 지원 되는 인증서가 필요 합니다. 2013 릴리스, Lync Server 2013 및 Exchange 2013 및 SharePoint Server를 비롯 한 기타 Microsoft 서버 제품은 서버 간 인증 및 권한 부여를 위한 개방형 권한 부여 (OAuth) 프로토콜을 지원 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.

Windows 7 운영 체제, Windows Server 2008 운영 체제, Windows Server 2008 R2 운영 체제, Windows Vista 운영 체제, Microsoft Lync Phone Edition을 실행 하는 클라이언트에서 연결 하는 경우 Lync Server 2013에 대 한 지원이 포함 되지만 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서가 필요 합니다. SHA-256를 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 SHA-256를 사용 하 여 공용 CA에서 발급 합니다.

다음 표에는 프런트 엔드 풀 및 스탠더드 버전 서버에 대 한 서버 역할별 인증서 요구 사항이 나와 있습니다. 이러한 모든 기능을 표준 웹 서버 인증서, 개인 키, 내보낼 수 없는 것입니다.

인증서 마법사를 사용 하 여 인증서를 요청할 때 EKU (서버 확장 키 사용)가 자동으로 구성 됩니다.

<div>


> [!NOTE]  
> 각 인증서 이름은 컴퓨터 스토어에서 고유 해야 합니다.



</div>

<div>


> [!NOTE]  
> DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com을 구성한 경우 인증서의 주체 대체 이름에이를 추가 해야 합니다.



</div>

### <a name="certificates-for-standard-edition-server"></a>스탠더드 버전 서버용 인증서

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
<th>인증</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>풀의 FQDN (정규화 된 도메인 이름)</p></td>
<td><p>풀의 FQDN과 서버의 FQDN</p>
<p>여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.</p>
<p>이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.</p></td>
<td><p>SN = se01; SAN = se01</p>
<p>이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p</p></td>
<td><p>스탠더드 버전의 서버에서 서버 FQDN은 풀 FQDN과 동일 합니다.</p>
<p>마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.</p>
<p>서버 간 인증에도이 인증서를 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>내부 웹 FQDN (서버의 FQDN과 동일)</p></li>
<li><p>간단한 Url 소개</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>관리 간단한 URL</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>SN = se01; SAN = se01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</p>
<p>와일드 카드 인증서 사용:</p>
<p>SN = se01; SAN = se01. SAN = *. m a c</p></td>
<td><p>토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수는 없습니다.</p>
<p>여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</p>
<p>간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>SIP 도메인당 간단한 Url 소개</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>SN = se01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</p>
<p>와일드 카드 인증서 사용:</p>
<p>SN = se01; SAN = webcon01. SAN = *. m a c</p></td>
<td><p>여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</p>
<p>간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>프런트 엔드 풀의 프론트 엔드 서버용 인증서

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
<th>인증</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>풀의 FQDN 및 서버의 FQDN입니다.</p>
<p>여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.</p>
<p>이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sipdomain (사용 하는 각 SIP 도메인)에 대 한 항목도 필요 합니다.</p></td>
<td><p>SN = eepool. m a c. SAN = eepool. m a c. SAN = ee01</p>
<p>이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p</p></td>
<td><p>마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.</p>
<p>서버 간 인증에도이 인증서를 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>내부 웹 FQDN (서버의 FQDN과 같지 않음)</p></li>
<li><p>서버 FQDN</p></li>
<li><p>Lync 풀 FQDN</p></li>
<li><p>간단한 Url 소개</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>관리 간단한 URL</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>SN = ee01; SAN = ee01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</p>
<p>와일드 카드 인증서 사용:</p>
<p>SN = ee01; SAN = ee01. SAN = *. m a c</p></td>
<td><p>여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</p>
<p>간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>관리 간단한 URL</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>SN = ee01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</p>
<p>와일드 카드 인증서 사용:</p>
<p>SN = ee01; SAN = webcon01. SAN = *. m a c</p></td>
<td><p>여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.</p>
<p>간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>디렉터에 대 한 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>인증</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>디렉터 풀의 FQDN</p></td>
<td><p>디렉터의 FQDN, 디렉터 풀의 FQDN</p>
<p>이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sipdomain (사용 하는 각 SIP 도메인)에 대 한 항목도 필요 합니다.</p></td>
<td><p>SN = dir-pool.contoso.com SAN = dir-pool.contoso.com SAN = dir01</p>
<p>이 디렉터 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a m;이 필요 합니다. SAN = sip. c a p</p></td>
</tr>
<tr class="even">
<td><p>웹 내부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>내부 웹 FQDN (서버의 FQDN과 동일)</p></li>
<li><p>서버 FQDN</p></li>
<li><p>Lync 풀 FQDN</p></li>
<li><p>간단한 Url 소개</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>관리 간단한 URL</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>SN = dir01; SAN = dir01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c</p>
<p>SN = dir01; SAN = dir01 SAN = * .com</p></td>
</tr>
<tr class="odd">
<td><p>웹 외부</p></td>
<td><p>서버의 FQDN</p></td>
<td><p>다음을 각각 수행 합니다.</p>
<ul>
<li><p>외부 웹 FQDN</p></li>
<li><p>전화 접속 간단한 URL</p></li>
<li><p>관리 간단한 URL</p></li>
<li><p>또는 간단한 Url의 와일드 카드 항목</p></li>
</ul></td>
<td><p>디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.</p>
<p>SN = dir01; SAN = directorwebcon01 SAN =. m a c. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c</p>
<p>SN = dir01; SAN = directorwebcon01 SAN = * .com</p></td>
</tr>
</tbody>
</table>


독립 실행형 중재 서버 풀을 사용 하는 경우에는 다음 표에 나열 된 인증서가 각 서버의 중재 서버에 필요 합니다. 프런트 엔드 서버와 중재 서버를 collocate 경우이 항목의 앞부분에 있는 "프런트 엔드 서버에 대 한 인증서" 표에 나열 된 인증서가 충분 합니다.

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
<th>인증</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>풀의 FQDN</p></td>
<td><p>풀의 FQDN</p>
<p>풀 구성원 서버의 FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net SAN = medsvr-pool.contoso.net SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable Branch 기기에 대 한 인증서

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>인증</th>
<th>주체 이름/일반 이름</th>
<th>주체 대체 이름</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본값</p></td>
<td><p>기기의 FQDN</p></td>
<td><p>SIP. &lt;SIPDOMAIN&gt; (SIP 도메인당 하나의 항목이 필요 함)</p></td>
<td><p>SN = sba01; SAN = sip. SAN = sip. c a p</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 와일드카드 인증서 지원](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

