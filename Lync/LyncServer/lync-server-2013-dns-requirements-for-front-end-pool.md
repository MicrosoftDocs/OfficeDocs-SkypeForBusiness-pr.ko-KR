---
title: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 882ffb0597b0dbd4f4be5b25a86facdda4367734
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-07_

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

토폴로지 작성기에 토폴로지를 게시 하기 전에 필요한 DNS (Domain Name System) 레코드를 구성 해야 합니다. 또한 Lync Server 2013 배포의 구성에 사용 되는 Fqdn (정규화 된 도메인 이름) 중 일부는 논리적 서버 Fqdn이 아니며, 게시 하기 전에 추가 DNS를 구성 해야 합니다.

<div>


> [!WARNING]  
> Lync Server 2013에서는 단일 레이블 도메인을 지원 하지 않습니다. 예를 들어 <STRONG>contoso.local</STRONG>이라는 루트 도메인으로 구성된 포리스트는 지원되지만 <STRONG>local</STRONG>이라는 루트 도메인은 지원되지 않습니다. 자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름을 사용 하 여 Windows 구성에 대 한 정보, <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&ampkbid = 300684</A>을 참조 하십시오.



</div>

<div>


> [!IMPORTANT]  
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. Lync Server, Edge 서버 및 풀을 실행 하는 서버의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용하지 마십시오. FQDN의 비표준 문자는 외부 DNS 및 공용 CA(인증 기관)에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).



</div>

토폴로지를 배포한 후 작동 하기 전에 특정 기능에 대 한 필요에 따라 다음과 같은 Active Directory 및 DNS 레코드가 만들어졌는지 확인 합니다.

  - 토폴로지에 있는 각 서버 역할은 Active Directory 개체로 게시 됩니다 (도메인에 컴퓨터를 가입 하면이 작업을 수행 하는 경우).

  - 각 서버에 대한 DNS A 레코드가 있어야 합니다.

  - \_Sipinternaltls\_tcp 형식의 클라이언트에 대해 자동 로그온을 사용 하려는 경우 각 SIP 도메인에 대해 DNS SRV 레코드가 존재 합니다. \<SIP 도메인\> 클라이언트에 대해 수동 구성을 사용하려는 경우에는 이 레코드가 필요하지 않습니다.

  - 구성된 각 단순 URL(모임 및 전화 접속)에 대한 DNS A 레코드가 있어야 합니다(일반적으로 meet, dialin, lwa, scheduler의 4가지). 또한 Lync Server 2013 제어판에 액세스 하기 위한 특수 URL 인 관리자 단순 URL이 있습니다.

  - SQL Server를 실행 하는 서버는 도메인에 가입 되어야 하며 토폴로지 작성기가 게시 하는 컴퓨터에서 연결할 수 있어야 합니다.

아래 표는 계획 섹션에 설명된 참조 아키텍처를 따릅니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 를 참조 하십시오.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>프런트 엔드 풀에 필요한 DNS 레코드

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>위치</th>
<th>유형</th>
<th>FQDN</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01(DNS 부하 분산). 풀에 있는 각 프런트 엔드 서버의 IP 주소에 대 한 DNS A 레코드가 있어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01(하드웨어 부하 분산 장치의 VIP(가상 IP))</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 프런트 엔드 서버 (노드 1)</p>
<p>Pool01 프런트 엔드 서버 (노드 2)</p>
<p>Pool01 프런트 엔드 서버 (노드 3)</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 프런트 엔드 서버 (노드 2)</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>클라이언트-서버 웹 트래픽용 Pool01(VIP)</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>SQL Server 2008 R2를 실행 하는 Pool01 백 엔드 서버</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Lync Phone Edition 또는 DNS SRV 레코드가 없는 클라이언트의 자동 로그온 및 엄격한 도메인 일치에 필요 합니다. 모든 경우에 반드시 필요한 것은 아닙니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>두 번째 SIP 도메인을 가정합니다. Lync Phone Edition, DNS SRV 레코드가 없는 클라이언트의 자동 로그온 및 엄격한 도메인 일치에 필요 합니다. 모든 경우에 반드시 필요한 것은 아닙니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>내부적으로 게시 된 전화 접속 회의에 대 한 단순 URL-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>내부적으로 게시 된 회의에 대 한 단순 URL-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>관리자로</p></td>
<td><p>선택적 레코드, Lync Server 2013 제어판에 게시 된 내부-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다. 도메인 이름 없이 호스트 이름만 사용하는 것이 좋습니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = 하드웨어 부하 분산 장치의 가상 IP 주소



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>프런트 엔드 풀에 대 한 DNS SRV 레코드


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>위치</th>
<th>유형</th>
<th>FQDN</th>
<th>대상 FQDN</th>
<th>포트</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp. contoso.</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>내부적으로 작동 하도록 Lync 2013 클라이언트를 자동으로 구성 하는 데 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>내부적으로 작동 하도록 Lync 2013 클라이언트를 자동으로 구성 하는 데 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _udp. contoso.</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Lync Phone Edition을 실행 하는 장치에 필요한 NTP (네트워크 시간 프로토콜) 원본입니다. 내부적으로 도메인 컨트롤러를 가리켜야 합니다. 도메인 컨트롤러가 정의되어 있지 않은 경우에는 NTP 서버 time.windows.com을 사용합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

