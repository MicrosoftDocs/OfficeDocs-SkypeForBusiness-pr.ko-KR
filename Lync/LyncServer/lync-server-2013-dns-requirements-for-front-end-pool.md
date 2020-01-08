---
title: 'Lync Server 2013: 프런트 엔드 풀에 대한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀에 대한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-07_

이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.

토폴로지 작성기에 토폴로지를 게시 하기 전에 필수 DNS (Domain Name System) 레코드를 구성 해야 합니다. 또한 Lync Server 2013 배포의 구성에 사용 되는 Fqdn (정규화 된 도메인 이름) 중 일부는 논리적이 고 비 실제 서버 Fqdn 이므로 게시 하기 전에 추가 DNS 구성이 필요 합니다.

<div>


> [!WARNING]  
> Lync Server 2013는 단일 레이블이 지정 된 도메인을 지원 하지 않습니다. 예를 들어, <STRONG>contoso. local</STRONG> 이라는 루트 도메인이 있는 포리스트는 지원 되지만 <STRONG>local</STRONG> 이라는 루트 도메인은 지원 되지 않습니다. 자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름을 사용 하 여 Windows 구성에 대 한 정보" <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp, kbid = 300684</A>을 참조 하세요.



</div>

<div>


> [!IMPORTANT]  
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입 되어 있지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. Lync Server, Edge 서버 및 풀을 실행 하는 서버의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용 하지 마세요. FQDN의 비표준 문자는 외부 DNS 및 Ca (공개 인증 기관)에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).



</div>

토폴로지를 배포한 후에 작동 하기 전에 다음 Active Directory 및 DNS 레코드가 만들어졌는지 확인 하세요 (특정 기능에 대 한 요구 사항에 따라 결정).

  - 토폴로지에 존재 하는 각 서버 역할은 Active Directory 개체로 게시 됩니다 (도메인에 컴퓨터를 참가 하면이를 수행 하 게 됩니다).

  - 각 서버에 대 한 DNS A 레코드가 있습니다.

  - \_Sipinternaltls\_tcp 형식의 클라이언트에 대 한 자동 로그온을 사용 하려는 경우 각 SIP 도메인에 대 한 DNS SRV 레코드가 있습니다. \<SIP 도메인\>. 클라이언트에 수동 구성을 사용 하는 경우에는이 레코드가 필요 하지 않습니다.

  - 일반적으로 모임, 전화 접속, lwa, 스케줄러 등의 구성 된 각 단순 URL에 대 한 DNS A 레코드입니다. 또한 Lync Server 2013 제어판에 대 한 액세스를 위한 특별 한 URL 인 관리 간단한 URL이 있습니다.

  - SQL Server를 실행 하는 서버는 도메인에 가입 하 고 토폴로지 작성기가 게시 하는 컴퓨터에서 연결할 수 있어야 합니다.

테이블은 계획 섹션에 제시 된 참조 아키텍처를 따릅니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 를 참조 하세요.

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
<th>Q</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS 로드 균형 조정). 풀에 속한 각 프런트 엔드 서버의 IP 주소에 대 한 DNS A 레코드가 있어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (하드웨어 로드 균형 조정기의 VIP (가상 IP)).</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 프런트 엔드 서버 (노드 1).</p>
<p>Pool01 프런트 엔드 서버 (노드 2).</p>
<p>Pool01 프런트 엔드 서버 (노드 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 프런트 엔드 서버 (노드 2).</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>클라이언트 대 서버 웹 트래픽에 대 한 Pool01 (VIP).</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>SQL Server 2008 R2를 실행 하는 Pool01 백 엔드 서버입니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Lync Phone Edition 또는 DNS SRV 레코드가 없는 클라이언트의 자동 로그온과 엄격한 도메인 일치에 필요 합니다. 모든 경우에 필요 하지는 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>두 번째 SIP 도메인으로 간주 합니다. Lync Phone Edition, DNS SRV 레코드가 없는 클라이언트의 자동 로그온, 엄격한 도메인 일치에 필요 합니다. 모든 경우에 필요 하지는 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>내부적으로 게시 된 전화 접속 회의에 대 한 간단한 URL – 프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 간단한 URL 쿼리에 응답 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>내부적으로 게시 되는 회의에 대 한 간단한 URL – 프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 간단한 URL 쿼리에 응답 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>에서</p></td>
<td><p>admin.contoso.com</p>
<p>관리자</p></td>
<td><p>선택적 레코드, Lync 2013 Server 용 간단한 URL-프런트 엔드 서버 (또는 설치 되어 있는 경우)가 단순 URL 쿼리에 응답 하 여이를 내부적으로 게시할 수 있습니다. 호스트 이름만 (도메인 이름 없음) 하는 것이 좋습니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = 하드웨어 부하 분산 장치에 대 한 가상 IP 주소



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
<th>Q</th>
<th>대상 FQDN</th>
<th>포트</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp. m m .com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>내부적으로 작업 하도록 Lync 2013 클라이언트를 자동 구성 하는 데 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp. c a m</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>내부적으로 작업 하도록 Lync 2013 클라이언트를 자동 구성 하는 데 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>내부 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _udp. m m .com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Lync Phone Edition을 실행 하는 장치에 필요한 NTP (네트워크 시간 프로토콜) 원본입니다. 내부적으로이는 도메인 컨트롤러를 가리켜야 합니다. 도메인 컨트롤러가 정의 되지 않은 경우에는 NTP 서버 time.windows.com를 사용 하려고 시도 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

