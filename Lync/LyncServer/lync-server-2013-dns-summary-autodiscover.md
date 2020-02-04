---
title: 'Lync Server 2013: DNS 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS 요약-Lync Server 2013의 자동 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-13_

자동 검색은 HTTP 또는 HTTPS를 통한 통신을 허용 하는 유연한 서비스입니다. 이를 위해서는 DNS (domain name system) 및 자동 검색 서비스를 호스트 하는 서버에서 사용 하는 인증서가 올바르게 구성 되어 있어야 합니다. 인증서 요구 사항은 [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)에 설명 되어 있습니다.

<div>


> [!IMPORTANT]  
> Lync 서버 클라이언트에 대 한 DNS 조회 논리는 특정 해상도 순서를 사용 합니다. 항상 lyncdiscoverinternal를 포함 해야 합니다. &lt;도메인과&gt; lyncdiscover. &lt;DNS&gt; 의 도메인 Lyncdiscoverinternal를 제외 합니다. &lt;도메인&gt; 레코드를 사용 하면 내부 클라이언트가 의도 한 서비스에 연결 되지 않거나 잘못 된 자동 검색 응답을 받을 수 없습니다.



</div>

### <a name="internal-dns-records"></a>내부 DNS 레코드

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름</th>
<th>(으)로 확인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</p></td>
<td><p>디렉터 풀에 대 한 내부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A (host, if IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</p></td>
<td><p>디렉터 풀 (부하 분산 장치를 사용 하는 경우)의 내부 웹 서비스 IP 주소 (VIP (가상 IP) 주소) 또는 사용자가 디렉터를 보유 하 고 있지 않은 경우 프런트 엔드 풀 중 하나에 해당 하는 경우</p></td>
</tr>
</tbody>
</table>


다음 외부 DNS 레코드 중 하나를 만들어야 합니다.

### <a name="external-dns-records"></a>외부 DNS 레코드

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>레코드 종류</th>
<th>호스트 이름</th>
<th>(으)로 확인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A (host, if IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>역방향 프록시의 외부 또는 공용 IP 주소입니다.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 외부 트래픽은 리버스 프록시를 거칩니다.



</div>

<div>


> [!NOTE]  
> 모바일 장치 클라이언트는 서로 다른 도메인의 여러 SSL (Secure Sockets Layer) 인증서를 지원 하지 않습니다. 따라서 HTTPS를 통해 다른 도메인으로의 CNAME 리디렉션이 지원 되지 않습니다. 예를 들어, director.contoso.net의 주소로 리디렉션하는 lyncdiscover.contoso.com에 대 한 DNS CNAME 레코드는 HTTPS를 통해 지원 되지 않습니다. 이러한 토폴로지에서는 모바일 장치 클라이언트가 http를 통해 CNAME 리디렉션이 해결 되도록 첫 번째 요청에 대해 HTTP를 사용 해야 합니다. 그런 다음 후속 요청에서 HTTPS를 사용 합니다. 이 시나리오를 지원 하려면 포트 80 (HTTP)에 대 한 웹 게시 규칙을 사용 하 여 역방향 프록시를 구성 해야 합니다. 자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 이동성에 대 한 리버스 프록시를 구성 하는</A>"포트 80에 대 한 웹 게시 규칙 만들기"를 참조 하세요. 동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원 됩니다. 이 경우 대상 도메인의 인증서가 원래 도메인을 덮습니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모바일 기능에 대해 역방향 프록시 구성](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[인증서 요약-Lync Server 2013의 자동 검색](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

